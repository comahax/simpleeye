# simpleeye
A  simple blind exploit tool( a dns server and a web app)  thant all in one python file


单个python文件的cloudeeye 实现,支持http协议和dns协议 方式 进行 oob攻击；

首先在dns域名注册出自定义dns，填写自己的服务器公网ip，然后有几个配置项：

allowkeys web方式访问本服务的key,默认情况如果当前主机域名是e.qy.kim,那么web查看log地址是

e.qy.kim:8899/e_e  。  resolveconfig可以自定义域名解析记录，blacklist可以配置黑名单域名（系统不会记录解析这些域名的记录）。


resolveconfig={"e.qy.kim":"1.63.65.182"#这里可以配置一个服务器的ip,'qy.kim':"1.63.65.182"}

allowkeys=["e_e"]

blacklist=["x.qy.kim","e.qy.kim","ns1.qy.kim","ns2.qy.kim"]



如果域名是qy.kim，使用方式如下：
1,ping test.qy.kim

PS C:\Users\maocz> ping test.qc.kim

Pinging test.qc.kim [127.0.0.1] with 32 bytes of data:
Reply from 127.0.0.1: bytes=32 time<1ms TTL=128

Ping statistics for 127.0.0.1:
    Packets: Sent = 1, Received = 1, Lost = 0 (0% loss),
Approximate round trip times in milli-seconds:
    Minimum = 0ms, Maximum = 0ms, Average = 0ms
	
	
2,http://e.qy.kim:8899/jndi_oob_exploit



3,然后访问 http://e.qy.kim:8899/e_e 

web内容如下
————
dns

to weblog
test.qy.kim. 2017_12_07 03:16
**************************************************
to dns

weblog
/e_e 2017_12_07 03:17
/jndi_oob_exploit 2017_12_07 03:17

--


+++++++++++++++++++++
English:

#specify ip to  reserved  domins  
resolveconfig={"e.qy.kim":"1.63.65.182",'qy.kim':"1.63.65.182"}

#access key
allowkeys=["e_e"]

blacklist=["x.qy.kim","e.qy.kim","ns1.qy.kim","ns2.qy.kim"]





usage  

ping test.qy.kim

HTTP access   http://e.qy.kim:8899/jndi_oob_exploit

view access log http://e.qy.kim:8899/e_e 


web content
————
dns

to weblog

test.qy.kim. 2017_12_07 03:16

**************************************************
to dns


weblog
/e_e 2017_12_07 03:17

/jndi_oob_exploit 2017_12_07 03:17

--
