# Parameters

The Phabricator deployment package contains a sequence software (referred to as "components") required for Phabricator to run. The important information such as the component name, installation directory path, configuration file path, port, version, etc. are listed below.

## Path

### Phabricator

Phabricator installation directory: */data/wwwroot/phabricator*  
Phabricator configuration file: */data/wwwroot/phabricator/phabricator/conf/local/local.json*  

### PHP

PHP configuration file: */etc/php/7.2/apache2/php.ini*

### Apache

Apache vhost configuration file: */etc/apache2/sites-enabled/000-default.conf*  
Apache main configuration file: */etc/apache2/apache2.conf*  
Apache logs file: */var/log/apache2*

### MYSQL

MySQL installation directory: */usr/share/mysql*  
MySQL data directory: */data/mysql*  
MySQL configuration file: */etc/mysql/my.cnf*    
MySQL Web Management URL: *http://Internet IP:9090*, get credential from [Username and Password](/stack-accounts.md)


## Ports

These Ports is need when use Phabricator, refer to [Safe Group Setting on Cloud Console](https://support.websoft9.com/docs/faq/tech-instance.html)

| Name | Number | Use |  Necessity |
| --- | --- | --- | --- |
| MySQL | 3306 | Remote connect MySQL | Optional |
| HTTP | 80 | HTTP requests for Phabricator | Required |
| HTTPS | 443 | HTTPS requests Phabricator | Optional |
| phpMyAdmin on Docker | 9090 | Web managment GUI for MySQL | Optional |

## Version

You can see the version from product page of Marketplace. However, after being deployed to your server, the components will be automatically updated, resulting in a certain change in the version number. Therefore, the exact version number should be viewed by running the command on the server:

```shell
# PHP Version
php -v

# Apache version:
apache2 -v

# MySQL version:
mysql -V

# Dokcer:
docker --version
```