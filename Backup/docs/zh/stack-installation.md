# 初始化安装

在云服务器上部署 Phabricator 预装包之后，请参考下面的步骤快速入门。

## 准备

1. 在云控制台获取您的 **服务器公网IP地址** 
2. 在云控制台安全组中，检查 **Inbound（入）规则** 下的 **TCP:80** 端口是否开启
3. 若想用域名访问 Phabricator，请先到 **域名控制台** 完成一个域名解析

## Phabricator 安装向导

1. 使用本地电脑的 Chrome 或 Firefox 浏览器访问网址：*http://域名* 或 *http://Internet IP*, 提示创建一个管理员账号（没有设置密码项，需要登录控制台后再设置）
   ![Phabricator初始化页面](https://libs.websoft9.com/Websoft9/DocsPicture/en/phabricator/phabricator-createadmin-websoft9.png)

2. 控制台顶部菜单会有一个"Unresolved Setup Issues"提示，有两个初始化项建议处理
   ![Phabricator 提示](https://libs.websoft9.com/Websoft9/DocsPicture/en/phabricator/phabricator-dashboard-websoft9.png)

3. 设置URI地址。依次打开：【Config】>【SETUP】>【Setup Issues】>【Base URI Not Configured】
   ![Phabricator URI](https://libs.websoft9.com/Websoft9/DocsPicture/en/phabricator/phabricator-url-websoft9.png)

4. 系统会生成一个设置URL的命令，复制命令，然后 SSH 远程登录到服务器中运行命名
   ![Phabricator URL](https://libs.websoft9.com/Websoft9/DocsPicture/en/phabricator/phabricator-urlcmd-websoft9.png)

5. 设置登录方式。依次打开：【Config】>【SETUP】>【Setup Issues】>【No Authentication Providers Configured】，根据提示完成后续设置
   ![Phabricator Authentication](https://libs.websoft9.com/Websoft9/DocsPicture/en/phabricator/phabricator-setautho-websoft9.png)

> 需要了解更多 Phabricator 的使用，请参考官方文档：[Phabricator Documentation](https://secure.phabricator.com/book/phabricator/)

## 常见问题

#### 浏览器打开IP地址，无法访问 Phabricator（白屏没有结果）？

您的服务器对应的安全组80端口没有开启（入规则），导致浏览器无法访问到服务器的任何内容

#### 本部署包采用的哪个数据库来存储 Phabricator 数据？

MySQL

#### Phabricator 初始化创建管理员账号步骤中为什么没有密码设置项？

需要登录到 Phabircator 控制台后再设置登录方式
