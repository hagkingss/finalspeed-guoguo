# FinalSpeed
FinalSpeed是高速双边加速软件,可加速所有基于tcp协议的网络服务,在高丢包和高延迟环境下,仍可达到90%的物理带宽利用率,即使高峰时段也能轻松跑满带宽.

### 安装教程
[客户端安装说明](https://www.91yun.org/archives/615)
<br />
[服务端安装说明](http://www.91yun.org/archives/2775)

### 说明


finalspeed作者开始卖收费版了，所以停止了免费版的更新，并且删除了所有代码。不过还好我fork了一份。。作为Openvz的救星，还是有不少人对finalspeed有需求的。所以我就做了这个一键安装包。

这个一键安装包完全重写了作者原来的安装代码，启动，停止代码。并加入了服务，可以使用 service finalspeed star | stop 来控制，加入了开机启动启动。总之，你需要做的就是真正的一键。一键安装包安装的服务器端版本为1.2.需要1.0的自行到github下载。欢迎大家测试，有问题及时留言给我。

github地址：https://github.com/91yun/finalspeed

github里也有服务器端和客户端的文件。大家有需求可以自行去下载。


### 一键安装代码：
```
wget -N --no-check-certificate https://raw.githubusercontent.com/91yun/finalspeed/master/install_fs.sh && bash install_fs.sh
```
###一键卸载代码
```
wget -N --no-check-certificate https://raw.githubusercontent.com/91yun/finalspeed/master/install_fs.sh && bash install_fs.sh uninstall
```
### finalspeed操作命令

启动： /etc/init.d/finalspeed start

停止命令：/etc/init.d/finalspeed stop

状态命令（查看日志）：/etc/init.d/finalspeed status

### finalspeed安装路径

安装路径： /fs/

日志路径：/fs/server.log

################################网络版使用教程#####################################################
FinalSpeed 是双边加速软件，不仅需要服务器端，还需要在电脑上安装客户端，这不如锐速方便和适用性。（手机上没有相应的 app ，所以就用不了啦）

一定要使用客户端配合服务器端，否则没有任何加速效果

FinalSpeed 目前无论是服务器端和客户端都支持 windows 和 linux ，客户端还支持 osx

FinalSpeed 有两种加速模式 tcp 加速和 udp 加速， Openvz 只能用 udp 加速，不过效果也很明显，锐速是无法使用在 Openvz 的 vps 上的。

目前用 hostus 的 hk 测试了下效果显著，没加速前看 youtube 的 1080p 都卡死，加速后可顺畅观看 4k 视频。

安装
wget –N —no–check–certificate https://raw.githubusercontent.com/91yun/finalspeed/master/install_fs.sh && bash install_fs.sh
卸载
wget –N —no–check–certificate https://raw.githubusercontent.com/91yun/finalspeed/master/install_fs.sh && bash install_fs.sh uninstall
finalspeed 操作命令
启动： /etc/init.d/finalspeed start

停止命令： /etc/init.d/finalspeed stop

状态命令（查看日志）： /etc/init.d/finalspeed status

finalspeed 安装路径
安装路径： /fs/

日志路径： /fs/server.log

客户端下载和安装
下载地址 :
finalspeed_install1.0.exe

finalspeed_install1.2.exe

如果大家觉的 1.2 的不稳定可以换回 1.0 的使用

FinalSpeed 客户 端 Java 版 , 支持 OS X,Linux
下载地址 :
finalspeed_client1.0.zip

系统需安装 java 运行环境 ,Linux 还需安装 libpcap.
Ubuntu,Debian 安装 libpcap: apt-get -y install libpcap-dev
Centos 安装 libpcap: yum -y install libpcap

安装 : 下载解压 .
运行 : 打开终端 , 假设 finalspeed_client.jar 所在路径为 /fsclient , 先切换到该路径 cd /fsclient ,
然后执行 sudo java -jar finalspeed_client.jar , 前面加 sudo, 因为必须以 root 权限运行 , 如果没有 root 权限 , 会无法启用 tcp 协议 .

———————————————————————————-

注意问题 , 必读 !
1. 服务器必须同时部署 FinalSpeed 服务端才能进行加速 .
2. 客户端必须准确设置物理带宽 , 最终加速的速度不会超过所设置的带宽值 , 如果设置值高于实际带宽会造成丢包 , 导致速度变慢 .
3. 客户端首选 tcp 协议 , 如果 udp 不稳定 , 请切换到 tcp.
4. 若服务器为 openvz 架构 , 客户端只能选择 udp 协议 , 其他架构同时支持 tcp 和 udp 协议 .
5.windows 客户端使用 tcp 协议时不兼容锐速 , 停止锐速后可以正常运行 .
6.FinalSpeed 不提供加密功能 , 如有安全需求 , 不要直接加速明文协议 .

———————————————————————————-

加速 ss 教程
假设服务器 IP 为 10.10.10.10,finalspeed 端口为默认 150,ss 端口为 8989.
加速前提 ss 服务端运行正常 ,ss 客户端也能正常登录 .
1. 运行 FinalSpeed 客户端 , 填写服务器地址 10.10.10.10 .

2. 点击添加 , 增加加速端口 , 加速端口为 ss 端口 8989, 如果为其他端口 , 请相应修改 , 本地端口任意 , 这里是 2000 .

3. 打开 ss 客户端 , 添加服务器 , 服务器 IP 为 127.0.0.1, 服务器端口为加速端口对应的本地端口 , 这里是 2000, 然后设置你的 ss 密码 , 加密方式 .

5. 确定保存 , 选择使用刚添加的服务器 , 并设置浏览器代理 , 成功连接后 ,FinalSpeed 状态栏会出现 ” 连接服务器成功 ” 提示 .

———————————————————————————-

加速 ssh 教程
假设服务器 IP 为 10.10.10.10,finalspeed 端口为默认 150,ssh 端口为 22.
1. 运行 FinalSpeed 客户端 , 填写服务器地址 10.10.10.10 .

2. 点击添加 , 增加加速端口 , 加速端口为 ssh 的监听端口 22, 本地端口任意 , 这里是 1000 .

3. 运行 ssh 客户端 , 增加连接 , 主机为 127.0.0.1, 端口号为加速端口对应的本地端口 , 这里是 1000, 设置如下 .

4. 设置完成后 , 输入 ssh 账号 , 密码 , 成功连接 ,FinalSpeed 状态栏会出现 ” 连接服务器成功 ” 提示 .

