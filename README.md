# 路由器部署op安装固件
 
a.https://firmware-selector.immortalwrt.org/   (下载适用于您设备的 ImmortalWrt 固件)

b. https://github.com/jerrykuku/luci-theme-argon/   (全新的 OpenWrt LuCI 主题)

c. https://github.com/xiaorouji/openwrt-passwall/releases/   (passwall)

d. https://github.com/vernesong/OpenClash?tab=readme-ov-file   (openclash)

e. https://github.com/nikkinikki-org/OpenWrt-nikki/blob/main/README.zh.md  (nikki)

## 安装OpenWrt原版之后以下命令


```shell
./scripts/feeds update luci
 ```


```shell
 ./scripts/feeds install -a -p luci
```


# passwall


## 重启OpenWrt之后运行刷新软件包！

1.到https://github.com/xiaorouji/openwrt-passwall/releases/  (passwall)

2.到https://github.com/xiaorouji/openwrt-passwall2/releases/   (passwall2)

下载 luci-19.07_luci-app-passwall_25.7.4-1_all.ipk重命名为∶luci-app-passwall_all.ipk  上传安装。

再下载  luci-19.07_luci-i18n-passwall-zh-cn_25.7.4-1_all.ipk  重命名为∶luci-i18n-passwall-zh-cn_all.ipk  上传安装。


# openclash

# 请先安装好这些依赖

## 以下命令


```shell
#iptables
opkg update
opkg install bash iptables dnsmasq-full curl ca-bundle ipset ip-full iptables-mod-tproxy iptables-mod-extra ruby ruby-yaml kmod-tun kmod-inet-diag unzip luci-compat luci luci-base
opkg install /tmp/openclash.ipk
apk update
apk add bash iptables dnsmasq-full curl ca-bundle ipset ip-full iptables-mod-tproxy iptables-mod-extra ruby ruby-yaml kmod-tun kmod-inet-diag unzip luci-compat luci luci-base
apk add -q --force-overwrite --clean-protected --allow-untrusted /tmp/openclash.apk
```

```shell
#nftables
opkg update
opkg install bash dnsmasq-full curl ca-bundle ip-full ruby ruby-yaml kmod-tun kmod-inet-diag unzip kmod-nft-tproxy luci-compat luci luci-base
opkg install /tmp/openclash.ipk
apk update
apk add bash dnsmasq-full curl ca-bundle ip-full ruby ruby-yaml kmod-tun kmod-inet-diag unzip kmod-nft-tproxy luci-compat luci luci-base
apk add -q --force-overwrite --clean-protected --allow-untrusted /tmp/openclash.apk
```


## 依赖更新-命令


```shell
opkg update
```


## 按顺序安装以上依赖，每个依赖单独安装

https://github.com/vernesong/OpenClash?tab=readme-ov-file   (openclash)

下载 luci-app-openclash_0.46.115_all.ipk重命名为∶luci-app-openclash_all.ipk  上传安装。


# Nikki

## 环境要求

- OpenWrt >= 23.05
- Linux Kernel >= 5.13
- firewall4

## 安装和更新

### A. 从软件源安装（推荐）

1. 添加源


```shell
# 只需运行一次
wget -O - https://github.com/nikkinikki-org/OpenWrt-nikki/raw/refs/heads/main/feed.sh | ash
```

2. 安装


```shell
# for opkg
opkg install nikki
opkg install luci-app-nikki
opkg install luci-i18n-nikki-zh-cn
# for apk
apk add nikki
apk add luci-app-nikki
apk add luci-i18n-nikki-zh-cn
```


### B. 从发行版安装


```shell
wget -O - https://github.com/nikkinikki-org/OpenWrt-nikki/raw/refs/heads/main/install.sh | ash
```


## 卸载并重置


```shell
wget -O - https://github.com/nikkinikki-org/OpenWrt-nikki/raw/refs/heads/main/uninstall.sh | ash
```


## 如何使用

查看 [Wiki](https://github.com/nikkinikki-org/OpenWrt-nikki/wiki)

## 如何工作

1. 混入并更新配置文件。
2. 启动 Mihomo。
3. 设置定时重启。
4. 配置 IP 规则/路由。
5. 生成防火墙配置并应用。

注意上述步骤可能因配置而变动。

## 编译


```shell
# 添加源
echo "src-git nikki https://github.com/nikkinikki-org/OpenWrt-nikki.git;main" >> "feeds.conf.default"
# 更新并安装源
./scripts/feeds update -a
./scripts/feeds install -a
# 编译
make package/luci-app-nikki/compile
```


编译结果可以在`bin/packages/your_architecture/nikki`内找到。

## 依赖

- ca-bundle
- curl
- yq
- firewall4
- ip-full
- kmod-inet-diag
- kmod-nft-socket
- kmod-nft-tproxy
- kmod-tun

# OpenWrt LuCI 主题

## 链式-命令


```shell
$\&nbsp;opkg\&nbsp;update\&nbsp;\&\&\&nbsp;opkg\&nbsp;install\&nbsp;dnsmasq-full
$\&nbsp;apk\&nbsp;--update-cache\&nbsp;add\&nbsp;dnsmasq-full
```


## 安装 LuCI 18.06 (精益 LEDE )


```shell
wget --no-check-certificate https://github.com/jerrykuku/luci-theme-argon/releases/download/v1.8.2/luci-theme-argon_1.8.2-20230609_all.ipk
opkg install luci-theme-argon*.ipk
```


## 安装 OpenWrt 官方 SnapShots 和 ImmortalWrt


```shell
opkg install luci-compat
opkg install luci-lib-ipkg
wget --no-check-certificate https://github.com/jerrykuku/luci-theme-argon/releases/download/v2.3.2/luci-theme-argon_2.3.2-r20250207_all.ipk
opkg install luci-theme-argon*.ipk
```


## 安装 luci-app-argon-config


```shell
wget --no-check-certificate -O luci-app-argon-config_0.9_all.ipk https://github.com/jerrykuku/luci-app-argon-config/releases/download/v0.9/luci-app-argon-config_0.9_all.ipk
opkg install luci-app-argon-config*.ipk
```


## 上传安装

https://github.com/jerrykuku/luci-app-argon-config/releases/

下载luci-i18n-argon-config-zh-cn_git-22.114.24542-d1474ba_all.ipk重命名为∶luci-i18n-argon-config-cn.ipk  上传安装。

再https://github.com/jerrykuku/luci-theme-argon/releases/

下载 luci-theme-argon-2.4.3-r20250722.apk重命名为∶luci-theme-argon.apk  上传安装。

# openclash内核


```shell
#进入内核安装目录 
cd /etc/openclash/core/clash\_meta 
#下载内核安装包 
wget https://raw.githubusercontent.com/vernesong/OpenClash/core/dev/smart/clash-linux-amd64-v1.tar.gz 
#解压内核安装包 
tar -zxvf clash-linux-amd64-v1.tar.gz 
#给予最高权限 
chmod 777 clash 
```
