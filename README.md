# Phabricator 自动化安装与部署

本项目是由 [Websoft9](https://www.websoft9.com) 研发的 [Phabricator](https://www.phacility.com/) 自动化安装程序，开发语言是 Ansible。使用本项目，只需要用户在 Linux 上运行一条命令，即可自动化安装 Phabricator，让原本复杂的安装过程变得没有任何技术门槛。  

本项目是开源项目，采用 LGPL3.0 开源协议。

## 操作系统

## 配置要求

安装本项目，确保符合如下的条件：

| 条件       | 详情         | 备注                 |
| ---------- | ----------- | -------------------- |
| 操作系统   | Ubuntu18.04                          |                      |
| 公有云     | AWS, Azure, 阿里云, 华为云, 腾讯云   | 可选                 |
| 私有云     | KVM, VMware, VirtualBox, OpenStack   | 可选                 |
| 服务器配置 | 最低1核1G，安装时所需的带宽不低于10M | 建议采用按量100M带宽 |

## 组件

包含的核心组件为：Phabricator + MySQL + Apache + PHP + Docker + phpMyAdmin on Docker

更多请见：[参数表](/docs/zh/stack-components.md)

## 如何安装最新版本？

本项目通过下载 Phabricator 源码进行安装，下载链接存储在：[role/phabricator/default/main.yml](/roles/phabricator/defaults/main.yml)。我们会定期检查并测试官方版本的可用性，尽可能保证用户可以顺利安装最新版。

```
phabricator_download_url: "https://github.com/phabricator/phabricator-cms/releases/download/3.9.15/phabricator_3.9.15-Stable-Full_package.zip"
```

如果你发现不是最新版本，请到 phabricator 仓库 [release 页面](https://downloads.phabricator.org/)获取最新版源码下载链接，再修改 [main.yml](/roles/phabricator/defaults/main.yml) 中的 ```phabricator_download_url``` 变量值即可安装最新版 phabricator。

## Ansible安装指南

支持root用户、普通用户（+su权限提升）等两种账号模式，也支持密码和秘钥对登录方式。

## 管理指南

[中文](https://support.websoft9.com/docs/phabricator/zh) | [English](https://support.websoft9.com/docs/phabricator)