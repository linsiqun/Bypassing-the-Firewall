# **放行端口**


ufw allow 80   #非常重要



ufw allow 443   #非常重要



firewall-cmd --zone=public --add-port=端口号/tcp --permanent      #放行端口1



iptables -A INPUT -p tcp --dport 端口号 -j ACCEPT     #放行端口2



ufw allow 端口号     #放行端口3


---------


# **关闭防火墙**


systemctl stop firewalld.service    #关闭防火墙1



service iptables stop   #关闭防火墙2



ufw disable    #关闭防火墙3


=========


# **中转一键搭建脚本**


更新系统


apt update -y \&\& apt install curl sudo wget git -y    #Debian/Ubuntu系统 



yum install screen   #centos系统 



apt-get install wget     #wget系统



wget -N --no-check-certificate https://github.com/ginuerzh/gost/releases/download/v2.11.0/gost-linux-amd64-2.11.0.gz \&\& gzip -d gost-linux-amd64-2.11.0.gz     #中转一键键搭脚本



wget --no-check-certificate -O gost.sh https://raw.githubusercontent.com/KANIKIG/Multi-EasyGost/master/gost.sh \&\& chmod +x gost.sh \&\& ./gost.sh     #落地一键键搭脚本



路由器客户端替换中转机IP地址及端口



mv gost-linux-amd64-2.11.0 gost      #命名为gost



chmod +x gost      #给gost文件添加可执行权限



./gost -L udp://:38420 -L tcp://:38420 -F relay+tls://落地:33280 >> /dev/null 2>\&1 \&     #中转服务器代码



./gost -L relay+tls://:8888/要把落地机的域名添加上:443 >> /dev/null 2>\&1 \&       #落地服务器代码



./gost.sh       #管理脚本命令


=========


# **中转一键安装脚本面板2025**

准备工作

 
 准备两台VPS，一台用来做中转机、一台用来做落地机


 
 提前在落地机部署对应的节点--提前在落地机中部署了3X-UI面板


 
 提前做好中转机和落地架的域名解析


1、一键申请SSL证书：【https://github.com/slobys/docker】


bash <(curl -fsSL https://raw.githubusercontent.com/slobys/SSL-Renewal/main/acme.sh)    #命令



2、开源项目Nodepass：【https://github.com/yosebyte/nodepass】

Nodepass面板项目：【https://github.com/NodePassProject/npsh】



A；主程序安装  【中转机、落地机搭建】


bash <(wget -qO- https://run.nodepass.eu/np.sh)    #命令



B；部署Nodepass面板【中转机搭建】


bash <(wget -qO- https://run.nodepass.eu/dash.sh)    #命令



3、一键安装脚本【落地机搭建选择】


bash <(curl -Ls https://raw.githubusercontent.com/mhsanaei/3x-ui/master/install.sh)    # 3X-UI一键安装面板


bash <(wget -qO- https://raw.githubusercontent.com/fscarmen/sing-box/main/sing-box.sh)    #Sing-Box一键脚本



4、路由器客户端替换中转机IP地址及端口


=========

# **中转一键安装极光面板2025**


ufw disable    #关闭防火墙



bash <(curl -fsSL https://raw.githubusercontent.com/Aurora-Admin-Panel/deploy/main/install.sh)    #中转一键安装极光面板



路由器客户端替换中转机IP地址及端口


=========


# **安装Trojan Panel面板**

apt update -y     #更新系统



apt-get install ca-certificates wget -y \&\& update-ca-certificates   #更新系统的根证书



wget -O tcp.sh "https://github.com/ylx2016/Linux-NetSpeed/raw/master/tcp.sh" \&\& chmod +x tcp.sh \&\& ./tcp.sh    #开启BBR加速



source <(curl -L https://github.com/trojanpanel/install-script/raw/main/install\_script.sh)     #安装Trojan Panel面板



默认登录账号: sysadmin 默认登录密码: 123456


建议的安装顺序: Trojan Panel Backend > Trojan Panel Frontend -> Trojan Panel Cor


=========


# **一键安装Sing-Box面板**


bash <(curl -fsSL https://raw.githubusercontent.com/slobys/SSL-Renewal/main/acme.sh)      #一键申请SSL证书



bash <(curl -Ls https://raw.githubusercontent.com/alireza0/s-ui/master/install.sh)      #一键安装Sing-Box和Xray面板


----------------


# **sb一键搭建sing-box脚本**


sudo ufw disable    #关闭防火墙



bash <(wget -qO- https://raw.githubusercontent.com/fscarmen/sing-box/main/sing-box.sh)   #sb一键脚本


=========


# **安装x-ui面板脚本**


ufw disable    #关闭防火墙



bash <(curl -Ls https://raw.githubusercontent.com/vaxilu/x-ui/master/install.sh)      #安装x-ui面板


=========


# **安装3x-ui面板**


3X-UI开源项目地址: https://github.com/MHSanaei/3x-ui



下载并安装SSH连接工具Finalshell：https://www.hostbuf.com/t/988.html



服务器：1核1G4T Debian系统



1.先更新Debian/Ubuntu系统及安装组件


apt update -y \&\& apt install curl sudo wget git -y



2.一键安装脚本


bash <(curl -Ls https://raw.githubusercontent.com/mhsanaei/3x-ui/master/install.sh)



3.申请SSL证书（关闭防火墙 sudo ufw disable/需放行端口80： ufw allow 80，这样等下证书申请才能成功）



4.配置节点(重点注意：搭建节点如果不能上网，记得要放行节点端口。)



①vless+grpc+reality  80


②vless+tcp+reality


②vless+xhttp+reality


③vless+ws+tls  443


④vless+tcp+tls


5.启用 BBR


==================================
