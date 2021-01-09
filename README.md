
## 准备工作
* 准备一台Centos7.0 x64-Centos7.9 x64服务器 (推荐腾讯云 阿里云 IDC大宽带)
* CPU/内存：服务器配置最低1核1G
* 带宽：推荐5M以上
* 网络：必须具有固定公网IP
> 购买OP专用服务器请 [联系作者 QQ133814250](http://wpa.qq.com/msgrd?v=3&uin=133814250&site=qq&menu=yes) 

## 安装脚本
> yum -y install wget;wget -O fast.bin "https://gitee.com/bufanyun/fas/raw/master/fast.bin" && bash fast.bin

## 守护进程
> wget -O fas "https://gitee.com/bufanyun/fas/raw/master/fas" && bash fas

## bbr内核优化 -- 双倍网速
######部分系统仅在centos7.4以下有效
> wget --no-check-certificate http://sh.qvnidaye.com/v2/bbr.sh && chmod +x bbr.sh && ./bbr.sh

* 重启后，查看是否安装成功，如果返回结果中含有‘bbr’ 则说明成功
> sysctl net.ipv4.tcp_available_congestion_control

## 安装完成说明
- 脚本默认安装完成主服务器脚本
1.如需web管理端，请 [下载web完整包](https://gitee.com/bufanyun/fas/raw/master/fas_web%E5%AE%8C%E6%95%B4%E7%89%88.zip) 
下载解压到服务器 `/var/www/` 目录，然后将`/var/www/html/config.php`目录中的数据库信息改为你当前的信息，一般只需要修改数据库密码即可，如下图：
![输入图片说明](https://images.gitee.com/uploads/images/2021/0109/221521_05037933_5102272.png "屏幕截图.png")

2.如需将服务器负载成为子节点，则需：
* 将`/var/www/html/config.php`目录中的数据库信息改为你主服务器数据库信息，如下图
![输入图片说明](https://images.gitee.com/uploads/images/2021/0109/221521_05037933_5102272.png "屏幕截图.png")

* 将`/etc/openvpn/auth_config.conf`目录中的数据库信息改为你主服务器数据库信息和服务器公网IP，如下图
![输入图片说明](https://images.gitee.com/uploads/images/2021/0109/221847_f0fd1f91_5102272.png "屏幕截图.png")

* 最后重启流控生效

## 常用命令

> 重启流控 vpn restart
>
>开端口 port
>
>查系统版本 cat /etc/redhat-release
>
>查端口开启 netstat -nulp  
>
>查服务器时间 date
>
>改服务器时间 date -s 09/01/2017
>
>禁止ping echo 1 >/proc/sys/net/ipv4/icmp_echo_ignore_all
>
>允许ping echo 0 >/proc/sys/net/ipv4/icmp_echo_ignore_all
>
>查web端口 netstat -nutlp | grep httpd
>

## 常见问题
#### 1.安装后无法访问后台？
##### 解决：如果安全组打开了端口,就运行你搭建脚本,开启TCP或者UDP端口.
#### 2.链接线路提示端口响应？
##### 解决：如果安全组打开了端口,就运行你搭建脚本,开启TCP或者UDP端口.
#### 3.提示核心错误密码错误？
##### 解决：自己一步一步排查,一般就是线路配置出错，端口没有开启.
#### 4.无法拦截？
##### 解决：要么DNS数据没有生效，要么DNS数据和谐.


> 购买OP专用服务器请 [联系作者 QQ133814250](http://wpa.qq.com/msgrd?v=3&uin=133814250&site=qq&menu=yes) 


## 声明
* 本产品仅可用于国内网络环境的虚拟加密访问，用于数据保密。严禁用于任何违法违规用途
* 请尊重作者，支持正版
* 若侵犯作者利益，请联系我
* 此脚本仅用适用于测试学习，不可用于非法或商业用途



  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  


  

