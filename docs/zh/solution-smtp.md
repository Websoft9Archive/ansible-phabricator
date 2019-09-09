# SMTP

大量用户实践反馈，使用**第三方 SMTP 服务发送邮件**是一种最稳定可靠的方式。  

请勿尝试在服务器上安装sendmail等发邮件方案，因为邮件系统的路由配置受制与域名、防火墙、路由等多种因素制约，导致不稳定、不易维护、诊断故障困难。

下面以**网易邮箱**为例，提供设置 Phabricator 发邮件的步骤：

1. 在网易邮箱管理控制台获取 SMTP 相关参数
   ```
   SMTP host: smtp.163.com
   SMTP port: 465 or 994 for SSL-encrypted email
   SMTP Authentication: must be checked
   SMTP Encryption: must SSL
   SMTP username: websoft9@163.com
   SMTP password: #wwBJ8    //此密码不是邮箱密码，是需要通过163邮箱后台设置去获取的授权码
   ```
2. 使用 SFTP 工具连接到云服务器，进入：*/data/wwwroot/phabricator/phabricator* 目录  
3. 编辑这个目录下的 *mailers.json* 文件，修改其中默认 SMTP 模板参数，然后保存
4. 运行下面的命令
   ```
   # set smtp
   ./bin/config set --stdin cluster.mailers < mailers.json

   # restart service
   sudo systemctl restart phabricator-daemons
   ```
5. 设置完毕

更多邮箱设置（QQ邮箱，阿里云邮箱，Gmail，Hotmail等）以及无法发送邮件等故障之诊断，请参考由Websoft9提供的 [SMTP 专题指南](https://support.websoft9.com/docs/faq/zh/tech-smtp.html)  

Phabricator 官方对外发邮件有非常详细方案：[Configuring Outbound Email](https://secure.phabricator.com/book/phabricator/article/configuring_outbound_email/)