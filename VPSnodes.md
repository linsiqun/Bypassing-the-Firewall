# **Router Deployment OP Installation Firmware**


a. https://firmware-selector.immortalwrt.org/  #Download the ImmortalWrt firmware for your device

b. https://github.com/jerrykuku/luci-theme-argon/  #New OpenWrt LuCI theme

c. https://github.com/xiaorouji/openwrt-passwall/releases/  #passwall

d. https://github.com/vernesong/OpenClash?tab=readme-ov-file/  #openclash

e. https://github.com/nikkinikki-org/OpenWrt-nikki/blob/main/README.zh.md  #nikki


**1. To install all other package definitions, run: command**

(After installing the original OpenWrt version)

./scripts/feeds update luci

./scripts/feeds install -a -p luci


# **passwall**

**2. Restart OpenWrt and refresh the software package**

1. Go to https://github.com/xiaorouji/openwrt-passwall/releases/passwall

2. Go to https://github.com/xiaorouji/openwrt-passwall2/releases/passwall2

Download luci-19.07\_luci-app-passwall\_25.7.4-1\_all.ipk, rename it to luci-app-passwall\_all.ipk, upload and install.

Download luci-19.07\_luci-i18n-passwall-zh-cn\_25.7.4-1\_all.ipk, rename it to luci-i18n-passwall-zh-cn\_all.ipk, upload and install.


# **openClash**

**3. Restart OpenWrt**

Please install these dependencies first.


**Deployment Command**


**#iptables**

opkg update
opkg install bash iptables dnsmasq-full curl ca-bundle ipset ip-full iptables-mod-tproxy iptables-mod-extra ruby ruby-yaml kmod-tun kmod-inet-diag unzip luci-compat luci luci-base
opkg install /tmp/openclash.ipk

apk update
apk add bash iptables dnsmasq-full curl ca-bundle ipset ip-full iptables-mod-tproxy iptables-mod-extra ruby ruby-yaml kmod-tun kmod-inet-diag unzip luci-compat luci luci-base
apk add -q --force-overwrite --clean-protected --allow-untrusted /tmp/openclash.apk


**#nftables**

opkg update
opkg install bash dnsmasq-full curl ca-bundle ip-full ruby ruby-yaml kmod-tun kmod-inet-diag unzip kmod-nft-tproxy luci-compat luci luci-base
opkg install /tmp/openclash.ipk

apk update
apk add bash dnsmasq-full curl ca-bundle ip-full ruby ruby-yaml kmod-tun kmod-inet-diag unzip kmod-nft-tproxy luci-compat luci luci-base
apk add -q --force-overwrite --clean-protected --allow-untrusted /tmp/openclash.apk



Install the above dependencies in order, installing each dependency separately.

https://github.com/vernesong/OpenClash/releases

4.Next, download luci-app-openclash_0.46.115_all.ipk, rename it to luci-app-openclash_all.ipk, and upload it for installation.


# **nikki**
Deployment Requirements

OpenWrt 23.05 or later

Linux kernel 5.13 or later

Firewall4 Version


**Features**

Transparent proxy (redirect/TPROXY/TUN, IPv4 and/or IPv6)

Access Control

Configuration File Mixing

Configuration File Editor

Scheduled Reboot

Installation and Update

**A.Installing from the Source Website (Recommended)**
https://github.com/nikkinikki-org/OpenWrt-nikki/blob/main/README.zh.md


# Run only once


**Installation Commands**

wget -O - https://github.com/nikkinikki-org/OpenWrt-nikki/raw/refs/heads/main/feed.sh | ash

**You can install via shell commands or the LuCI "Package" menu**


# Install opkg

opkg install nikki

opkg install luci-app-nikki

opkg install luci-i18n-nikki-zh-cn


# for apk
apk add nikki

apk add luci-app-nikki

apk add luci-i18n-nikki-zh-cn



**B. Install from the distribution website**

wget -O - https://github.com/nikkinikki-org/OpenWrt-nikki/raw/refs/heads/main/install.sh | ash


**Uninstall and reset**

wget -O - https://github.com/nikkinikki-org/OpenWrt-nikki/raw/refs/heads/main/uninstall.sh | ash


# Add repository

echo "src-git nikki https://github.com/nikkinikki-org/OpenWrt-nikki.git;main" >> "feeds.conf.default"

# Update and install repository

./scripts/feeds update -a

./scripts/feeds install -a

# Compile

make package/luci-app-nikki/compile

The compiled results can be found in bin/packages/your_architecture/nikki.

Dependency deployment

ca-bundle

curl

yq

firewall4

ip-full

kmod-inet-diag

kmod-nft-socket

kmod-nft-tproxy

kmod-tun


# OpenWrt LuCI Theme


5. https://github.com/jerrykuku/luci-theme-argon/ **Brand new OpenWrt LuCI theme**


**Deployment Commands** # opkg

opkg update    #Refresh the package source


opkg install pkg    #Install a specific package


opkg remove pkg    #Uninstall a specific package



**Deployment Commands** # apk

apk update   #Refresh the package source


apk add pkg   #Install a specific package


apk del pkg   #Uninstall a specific package


# Deployment Commands


**xmlCopy** 

$\&nbsp;opkg\&nbsp;update\&nbsp;\&\&\&nbsp;opkg\&nbsp;install\&nbsp;dnsmasq-full

$\&nbsp;apk\&nbsp;--update-cache\&nbsp;add\&nbsp;dnsmasq-full


**Install for OpenWrt official SnapShots and ImmortalWrt** 

opkg install luci-compat
opkg install luci-lib-ipkg
wget --no-check-certificate https://github.com/jerrykuku/luci-theme-argon/releases/download/v2.3.2/luci-theme-argon_2.3.2-r20250207_all.ipk
opkg install luci-theme-argon*.ipk


**Install luci-app-argon-config** 

wget --no-check-certificate -O luci-app-argon-config_0.9_all.ipk https://github.com/jerrykuku/luci-app-argon-config/releases/download/v0.9/luci-app-argon-config_0.9_all.ipk
opkg install luci-app-argon-config*.ipk

wget --no-check-certificate -O luci-app-argon-config_0.9_all.ipk https://github.com/jerrykuku/luci-app-argon-config/releases/download/v0.9/luci-app-argon-config_0.9_all.apk
opkg install luci-app-argon-config*.apk


# Skin Download

from  https://github.com/jerrykuku/luci-app-argon-config/releases/   Next, download luci-i18n-argon-config-zh-cn_git-22.114.24542-d1474ba_all.ipk Rename it to luci-i18n-argon-config-cn.ipk and upload it for installation.

from  https://github.com/jerrykuku/luci-theme-argon/releases/   Next, download luci-theme-argon-2.4.3-r20250722.apk , rename it to luci-theme-argon.apk and upload it for installation.


# deployment commands

\# Enter the kernel installation directory

cd /etc/openclash/core/clash\_meta


\# Download the kernel installation package

wget https://raw.githubusercontent.com/vernesong/OpenClash/core/dev/smart/clash-linux-amd64-v1.tar.gz


\# Unzip the kernel installation package

tar -zxvf clash-linux-amd64-v1.tar.gz


\#Grant highest authority

chmod 777 clash
