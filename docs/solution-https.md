# SSL/HTTPS

Phabricator deployment package has installed the SSL module of Nginx and open Certificate Authority **[Let's Encrypt](https://letsencrypt.org/)** for you configure the HTTPS quickly and conveniently.

> In addition to the vhost configuration file, HTTPS settings do not need to modify any files in Nginx

## Simple Steps

If you want to use a free certificate, just run the one command `certbot` on your instance to start the HTTPS deployment.

If you have applied for a commercial certificate, complete the HTTPS configuration in just three steps:

1. Upload your certificate to the directory of your instance: */data/cert* 
2. Edit the vhost configuration file: */etc/apache2/sites-enabled/000-default.conf* 
3. Insert the **HTTPS template** into *VirtualHost{  }* and modify to your certificate path
 ``` text
   #-----HTTPS template start------------
   SSLEngine on
   SSLCertificateFile  /data/cert/www.mydomain.com.crt
   SSLCertificateKeyFile  /data/cert/www.mydomain.com.key
   #-----HTTPS template end------------
   ```
4. Save file and [Restart Apache service](/admin-services.md)

## Special Guide

For details on configuring HTTPS pre-conditions, HTTPS configuration segment templates, precautions, detailed steps, and troubleshooting, refer to the [HTTPS Special Guide](https://support.websoft9.com/docs/faq/tech-https.html#apache) provided by Websoft9 