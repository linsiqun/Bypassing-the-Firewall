# 放行端口

```shell
ufw allow 80   #非常重要
```

```shell
 ufw allow 443   #非常重要
```

# 中转一键搭建脚本

## 更新-以下命令

```shell
 apt update -y \&\& apt install curl sudo wget git -y    #Debian/Ubuntu系统 
```

```shell
 wget -N --no-check-certificate https://github.com/ginuerzh/gost/releases/downloadv2.11.0gost-linux-amd64-2.11.0.gz && gzip-d gost-linux-amd64-2.11.0.gz     #中转一键键搭脚本
```

```shell
 wget --no-check-certificate -O gost.sh https://raw.githubusercontent.com/KANIKIG/Multi-EasyGost/master/gost.sh && chmod +x gost.sh && ./gost.sh     #中转一键安装脚本2
```

   
路由器客户端替换中转机IP地址及端口


./gost -L udp://:38420 -L tcp://:38420 -F relay+tls://落地:33280 >> /dev/null 2>\&1 \&     #中转服务器代码

  ./gost -L relay+tls://:8888/要把落地机的域名添加上:443 >> /dev/null 2>\&1 \&      #落地服务器代码


# 管理脚本命令


```shell
./gost.sh       #管理脚本命令
```


# 中转nodepass安装脚本面板2025


## 准备工作

      准备两台VPS，一台用来做中转机、一台用来做落地机

      提前在落地机部署对应的节点--提前在落地机中部署了3X-UI面板

      提前做好中转机和落地架的域名解析


## 一键申请SSL证书：【https://github.com/slobys/docker】

### 证书以下命令


```shell
 bash <(curl -fsSL https://raw.githubusercontent.com/slobys/SSL-Renewal/main/acme.sh)    #证书命令
```


开源项目Nodepass：【https://github.com/yosebyte/nodepass】

Nodepass面板项目：【https://github.com/NodePassProject/npsh】


## 主程序安装  【中转机、落地机搭建】

```shell
 bash <(wget -qO- https://run.nodepass.eu/np.sh)     #主程序命令
```

## 或


```shell
 bash <(curl -sSL https://run.nodepass.eu/np.sh)      #主程序命令
```


## 部署Nodepass面板【中转机搭建】



```shell
 bash <(wget -qO- https://run.nodepass.eu/dash.sh) install     #中转机命令
```


## 或


```shell
 bash <(curl -sSL https://run.nodepass.eu/dash.sh) install     #中转机命令
```


## 一键安装脚本【落地机搭建选择】

### 3X-UI一键安装面板


```shell
bash <(curl -Ls https://raw.githubusercontent.com/mhsanaei/3x-ui/master/install.sh)     # 3X-UI一键安装面板
```


### Sing-Box一键脚本


```shell
bash <(wget -qO- https://raw.githubusercontent.com/fscarmen/sing-box/main/sing-box.sh)     #Sing-Box一键脚本
```


路由器客户端替换中转机IP地址及端口


### 远程版本更新。


```shell
bash <(curl -sSL https://run.nodepass.eu/dash.sh) update     #版本更新
```


### 重置密码


```shell
bash <(curl -sSL https://run.nodepass.eu/dash.sh) resetpwd     #重置密码
```


# 中转一键安装极光面板

   
## 关闭防火墙
```shell
ufw disable     #关闭防火墙
```


## 安装极光面板


```shell
bash <(curl -fsSL https://raw.githubusercontent.com/Aurora-Admin-Panel/deploy/main/install.sh)     #中转一键安装极光面板
```


路由器客户端替换中转机IP地址及端口


# 安装Trojan Panel面板

## 更新


```shell
apt update -y     #更新系统
```



更新系统的根证书



```shell
apt-get install ca-certificates wget -y && update-ca-certificates     #更新系统的根证书
```



## 开启BBR加速




```shell
wget -O tcp.sh "https://github.com/ylx2016/Linux-NetSpeed/raw/master/tcp.sh" && chmod +x tcp.sh && .tcp.sh     #开启BBR加速
```


## Trojan Panel联机（推荐）



```shell
source <(curl -L https://github.com/trojanpanel/install-script/raw/main/install_script.sh)     #联机Trojan Panel面板
```

    

## Trojan Panel单机



```shell
source <(curl -L https://github.com/trojanpanel/install-script/raw/main/install_script_standalone.sh)     #单机Trojan Panel面板
```



     默认登录账号: sysadmin 默认登录密码: 123456

     建议的安装顺序: Trojan Panel Backend > Trojan Panel Frontend -> Trojan Panel Cor



#  一键安装Sing-Box面板


## 申请SSL证书



```shell
bash <(curl -fsSL https://raw.githubusercontent.com/slobys/SSL-Renewal/main/acme.sh)     #一键申请SSL证书
```


## 一键安装Sing-Box和Xray面板


```shell
bash <(curl -Ls https://raw.githubusercontent.com/alireza0/s-ui/master/install.sh)     #一键安装Sing-Box和Xray面板
```


# sb一键脚本部署


## 关闭防火墙


```shell
sudo ufw disable
```


## sb一键脚本


```shell
bash <(wget -qO- https://raw.githubusercontent.com/fscarmen/sing-box/main/sing-box.sh)     #sb一键脚本
```

     
# 安装x-ui面板


## 关闭防火墙


```shell
ufw disable
```


```shell
bash <(curl -Ls https://raw.githubusercontent.com/vaxilu/x-ui/master/install.sh)     #安装x-ui面板
```

 
# 安装x-ui面板

服务器:1核,1G 4T Debian 系统

首先,更新 Debian/Ubuntu 系统并安装组件。



```shell
apt update -y &&apt install curl sudo wget git -y     #更新
```



## 一键安装面板



```shell
bash <(curl -Ls https://raw.githubusercontent.com/mhsanaei/3x-ui/master/install.sh)     #3x-ui 面板
```
 

申请 SSL 证书(禁用防火墙 (sudo) ufw 禁用 ) / 允许访问端口 80 (ufw 允许 80) 证书 申请成功)。

 配置节点(重要:如果节点无法访问 Internet,请记住允许访问节点端口。

 ①vless+grpc+reality 80

②vless+tcp+reality

②vless+xhttp+reality

③vless+ws+tls 443

④vless+tcp+tls 



