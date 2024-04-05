1.扫描所有端口

`sudo nmap -p- 127.0.0.1`

2.服务版本信息

`sudo nmap -sV 127.0.0.1`

3.排除特定的ip

`nmap 192.168.43.0/24 --exclude 192.168.43.80`

`nmap 192.168.43.0/24 --excludefile list.txt`

4.更改扫描ip

`nmap --send-ip 192.168.43.80`

5.猜测主机所使用的操作系统

`nmap -O --osscan-guess 127.0.0.1`

