# OpenWrt-K

[![GitHub Repo stars](https://img.shields.io/github/stars/chenmozhijin/OpenWrt-K)](https://github.com/chenmozhijin/OpenWrt-K/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/chenmozhijin/OpenWrt-K)](https://github.com/chenmozhijin/OpenWrt-K/forks?include=active%2Carchived%2Cinactive%2Cnetwork&page=1&period=2y&sort_by=stargazer_counts)
[![GitHub commit activity (branch)](https://img.shields.io/github/commit-activity/t/chenmozhijin/OpenWrt-K)](https://github.com/chenmozhijin/OpenWrt-K/commits)
[![GitHub last commit (by committer)](https://img.shields.io/github/last-commit/chenmozhijin/OpenWrt-K)](https://github.com/chenmozhijin/OpenWrt-K/commits)
[![Workflow Status](https://github.com/chenmozhijin/OpenWrt-K/actions/workflows/build-openwrt.yml/badge.svg)](https://github.com/chenmozhijin/OpenWrt-K/actions)
> OpenWRT软件包与固件自动云编译

## 目录

[README](https://github.com/chenmozhijin/OpenWrt-K#openwrt-k):

1. [更新日志](https://github.com/chenmozhijin/OpenWrt-K#%E6%9B%B4%E6%96%B0%E6%97%A5%E5%BF%97)
2. [固件介绍](https://github.com/chenmozhijin/OpenWrt-K#%E5%9B%BA%E4%BB%B6%E4%BB%8B%E7%BB%8D)
  
[Wiki页面](https://github.com/chenmozhijin/OpenWrt-K/wiki):

1. [固件使用方法](https://github.com/chenmozhijin/OpenWrt-K/wiki/%E5%9B%BA%E4%BB%B6%E4%BD%BF%E7%94%A8%E6%96%B9%E6%B3%95)
2. [仓库基本介绍](https://github.com/chenmozhijin/OpenWrt-K/wiki/%E4%BB%93%E5%BA%93%E5%9F%BA%E6%9C%AC%E4%BB%8B%E7%BB%8D)
3. [定制编译OpenWrt固件](https://github.com/chenmozhijin/OpenWrt-K/wiki/%E5%AE%9A%E5%88%B6%E7%BC%96%E8%AF%91-OpenWrt-%E5%9B%BA%E4%BB%B6)
4. [常见问题](https://github.com/chenmozhijin/OpenWrt-K/wiki/%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98)

## 更新日志

[2025/2/7]升级openwrt到v24.10.0,修复AdGuardHome规则下载错误导致其无法启动的问题,增减部分软件包
<details><summary>增减列表</summary>

1. 删除:passwall、passwall2、luci-app-rclone、luci-app-ddns、luci-app-aria2(你可以通过修改编译配置把他们加回来)
2. 添加:luci-app-vlmcsd、luci-app-sqm、luci-app-qbittorrent

</details>
<details><summary>完整更新日志</summary>

[2024/9/26] 使用python重构了编译工作流,提高了可维护性, 优化了编译流程,减少资源占用  
[2023/7/27] 添加多配置编译支持,移动README部分内容到wiki
</details>

## 固件介绍

1. 基于OpenWrt官方源码编译
2. 自带丰富的LuCI插件与软件包（见内置功能）
3. 自带SmartDNS+AdGuard Home配置（AdGuard Home 默认密码：```password```）
4. 随固件编译几乎全部kmod（无sfe），拒绝kernel版本不兼容(kmod在Releases allkmod.zip中，建议与固件一同下载)
5. 固件自带OpenWrt-K工具支持升级官方源没有的软件包（使用```openwrt-k```命令）
6. 提供多种格式固件以应对不同需求

### 内置功能

已内置以下软件包：

1. LuCI插件：  
  [luci-app-adguardhome](https://github.com/chenmozhijin/luci-app-adguardhome) :AdGuardHome广告屏蔽工具的luci设置界面  
  [luci-app-argon-config](https://github.com/jerrykuku/luci-app-argon-config):Argon 主题设置  
  luci-app-cifs-mount：SMB/CIFS 网络挂载共享客户端  
  [luci-app-diskman](https://github.com/lisaac/luci-app-diskman)：DiskMan 磁盘管理  
  luci-app-fileassistant：文件助手  
  luci-app-firewall：防火墙  
  luci-app-netdata：[Netdata](https://github.com/netdata/netdata) 实时监控  
  [luci-app-netspeedtest](https://github.com/muink/luci-app-netspeedtest)：网速测试  
  luci-app-nlbwmon：网络带宽监视器
  [luci-app-openclash](https://github.com/vernesong/OpenClash):可运行在 OpenWrt 上的 Clash 客户端  
  luci-app-samba4：samba网络共享  
  [luci-app-smartdns](https://github.com/pymumu/luci-app-smartdns)：SmartDNS 服务器  
  [luci-app-socat](https://github.com/chenmozhijin/luci-app-socat)：Socat网络工具  
  luci-app-ttyd：ttyd 终端  
  [luci-app-turboacc](https://github.com/chenmozhijin/turboacc)：Turbo ACC 网络加速  
  luci-app-upnp：通用即插即用（UPnP）  
  luci-app-usb-printer：USB 打印服务器
  [luci-app-wechatpush](https://github.com/tty228/luci-app-wechatpush)：微信推送  
  luci-app-wol：网络唤醒  
  luci-app-zerotier：ZeroTier虚拟局域网
  luci-app-qbittorrent：qBittorrent-Enhanced-Edition的luci设置界面
  luci-app-sqm：Smart Queue Management (SQM) QoS
  luci-app-vlmcsd：VLMCSd KMS 激活工具

