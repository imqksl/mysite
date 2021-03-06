---
title: "创建 pve 模板"
date: 2020-03-19T18:06:36+08:00
tags: ["none"]
draft: true 

---

# 创建模板

安装一只小鸡

# 更新内核并启用 BBR-PLUS

参考一键脚本 [BBR+BBR魔改+Lotsever(锐速)一键脚本 for Centos/Debian/Ubuntu](https://www.moerats.com/archives/387/)或者[一键安装最新内核并开启 BBR 脚本](https://teddysun.com/489.html)

```bash
$ wget -N --no-check-certificate "https://raw.githubusercontent.com/chiakge/Linux-NetSpeed/master/tcp.sh" && chmod +x tcp.sh && ./tcp.sh
```

如果内核启动顺序不正确的话，可以[修改内核默认顺序](http://www.21yunwei.com/archives/5098)

# 完成初始化

```bash
# 安装 cloud-init
$ yum -y install cloud-init

# 重启
$ reboot

# 设置时区
```

# 模板和虚拟机的区别

虚拟机可以 `不可逆` 的转换为模板，模板无法开机，但可以通过模板克隆出新的虚拟机。

虚拟机和模板都可以克隆虚拟机，区别在于模板可以选择 `链接克隆` 和 `完整克隆`。而虚拟机只能 `完整克隆`。

# 参考链接

[proxmox里使用cloud-init和一些笔记](https://zhangguanzhang.github.io/2019/01/22/proxmox-cloud-init/#%E5%AE%89%E8%A3%85%E5%AE%8Cproxmox%E7%9A%84%E4%B8%80%E4%BA%9B%E8%AE%BE%E7%BD%AE)