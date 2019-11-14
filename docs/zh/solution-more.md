# 更多...

下面每一个方案，都经过实践证明行之有效，希望能够对你有帮助

## 域名绑定

绑定域名的前置条件是：Phabricator已经可以通过解析后的域名访问。  

虽然如此，从服务器安全和后续维护考量，**域名绑定**步骤不可省却  

Phabricator 域名绑定操作步骤：

1. 登录云服务器
2. 修改 [Apache虚拟机主机配置文件](/zh/stack-components.md#apache)，将其中的 **ServerName** 项的值 *www.example.com* 修改为你的域名
   ```text
    <VirtualHost *:80>
    ServerName www.example.com
    ...
    </VirtualHost>
   ```
3. 保存配置文件，重启[Apache服务](/zh/admin-services.md#apache)


## 迁移

暂无
