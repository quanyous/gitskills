# 通过ssh远程访问linux系统

说明：我尝试在一台老台式机装ubunto（台式机通过手机usb连接网络），在笔记本电脑上装xshell，试了很多次，也在csdn上找了很多方法，都没能连成功；后来我又在两台电脑的终端相互ping 对方的ip地址，然而都无法ping到；本来想放弃的，但还是在虚拟机上尝试一下，结果成功了，所以才有这篇笔记的诞生：

## 基本步骤：

1. 在pc端下载xshell 6（官网免费个体使用）并安装；

2. 打开xshell，新建会话，在主机上输入被访问linux 的IP；（在Linux输入ifconfig可get 到）

3. 在Linux上输入sudo apt-get install openssh-server 安装远程服务

4. 连接后输入被访问的Linux的用户名和密码；

5. 成功连接即可，为了测试一下，我在xshell 输入sudo apt install vim,结果虚拟机成功安装vim;

   ![1583990466286](C:\Users\沈有权\AppData\Roaming\Typora\typora-user-images\1583990466286.png)

   

   





























