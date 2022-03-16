# XScan

[使用文档](https://www.yuque.com/docs/share/a8a710bb-f2f6-4120-8d17-5fb639a061d8?)
## 前言
这是一个缝合怪

● go-crack
● fscan
● zscan
● kscan

参数说明
```
__   __      _____
\ \ / /     /  ___|
 \ V /______\ `--.  ___ __ _ _ __
 /   \______|`--. \/ __/ _` | '_ \
/ /^\ \     /\__/ / (_| (_| | | | |
\/   \/     \____/ \___\__,_|_| |_|

Version 1.0
Design By XTeam

Host is none
Usage of ./Xscan-Mac:
  -addr string
    	s5|http server addr (default "0.0.0.0:50000")
  -debug
    	open debug mode
  -domain string
    	rootkit.org
  -finger
    	Scab Web Finger
  -h string
    	IP ADDR: 10.0.0.1,10.0.0.5-10,192.168.1.*,192.168.10.1/24
  -hf string
    	-hf ip.txt
  -http-pass string
    	HttpPassword (default "qax")
  -http-user string
    	HttpUsername (default "qax")
  -httpdir string
    	http directory (default ".")
  -m string
    	-m portscan|-m ssh|-m all|-m title (default "all")
  -noping
    	no ping
  -o string
    	Scan OutPutFile (default "result.txt")
  -p string
    	Ports: 22,443|1-65535|3389 (default "21,22,23,80,81,88,135,139,468,443,445,1433,1523,3306,5432,7001,8001,8000,8080,8089,9200,11211,27017,1080,1214,13306,5000,5222,5900,5938,5984,6000,6379,7000,7070,8888,8088,8090,8222,8443,8545,8686,9000,9180,9200,9418,9999,10000,11115,8448,8484,8848,10183,15778,19313,8008,8009,8890,8891")
  -pass string
    	crack password
  -passfile string
    	password file
  -ping
    	using ping replace icmp
  -poc string
    	-poc weblogic,shiro
  -pocscanproxy string
    	-proxy http://127.0.0.1:8080
  -pocthread int
    	poc rate (default 20)
  -proxy string
    	vulnscan proxy
  -redisfile string
    	-redisfile id_rsa.pub
  -redisshell string
    	-redisshell 192.168.1.1:6666
  -shiro
    	Scan Shiro
  -skipportscan
    	Skip Port Scan-Scan Web Title
  -socks5-pass string
    	Socks5Password (default "qax")
  -socks5-user string
    	Socks5Username (default "qax")
  -sshcmd string
    	exec ssh cmd
  -t int
    	Thread nums (default 20)
  -timeout int
    	scan timeout (default 10)
  -urlfile string
    	url list
  -user string
    	crack username
  -userfile string
    	username file
  -vulnscan
    	Scan for web vulnerabilities(True|False)
  -webtimeout int
    	webscan timeout (default 20)
  -xscan string 
  		XScan Start password!
 ```
 
## 快速上手
默认扫描
指纹+shiro+漏扫
```
./xscan -h 192.168.123.22/24,192.168.123.1-255,192.168.122.1-192.168.123.254 -finger -vulnscan -shiro -xscan 360 -t 100
```
```
./xscan -hf ip.txt -finger -vulnscan -xscan 360 -t 100
```
指定密码
```
./xscan -h 192.168.123.22/24,192.168.123.1-255,192.168.122.1-192.168.123.254 -finger -vulnscan -xscan 360 -t 100 -user admin,root -pass 123456,root

./xscan -h 192.168.123.22/24,192.168.123.1-255,192.168.122.1-192.168.123.254 -finger -vulnscan -xscan 360 -t 100 -userfile user.txt -passfile pass.txt
```
指定模块
```
./xscan -h 192.168.123.22/24,192.168.123.1-255,192.168.122.1-192.168.123.254 -finger -vulnscan -xscan 360 -t 100 -m Web
```
-m参数指定模块只能选择一个,默认All
```
All 所有模块All In
Web 核心功能，可以扫描title和指纹以及shiro
MS17010 
SSH
SMB
MSSQL
MYSQL
FINDNET 
REDIS
ServerScan
urlscan 
```
## Spy模块
进入大内网以后,支持探测指定网段存活(ping .1和.255)
./xscan -h 192.168.123.22/24,192.168.123.1-255,192.168.122.1-192.168.123.254 -finger -vulnscan -xscan 360 -t 100 -m Spy

## Socks5模块
./Xscan-Mac -m socks5 ./Xscan-Mac -m socks5 -addr 0.0.0.0:6666 
默认密码 qax qax


## HTTP模块
./Xscan-Mac -m http -addr 0.0.0.0:6666
默认密码 qax qax

