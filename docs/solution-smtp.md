# SMTP

Sending mail is a common feature for Phabricator. After a large number of user practice feedback, only one way is recommended, that is, using the **third-party STMP service** to send the email.

> Do not try to install **Sendmail** or other Mail server software on your Cloud Server for sending mail, because it is very difficulty in maintenance.

Follow is the sample using **SendGrid's SMTP Service** to configure sending mail for Phabricator:

1. Log in SendGrid console, prepare your SMTP settings like the follow sample
   ```
   SMTP host: smtp.sendgrid.net
   SMTP port: 25 or 587 for unencrypted/TLS email, 465 for SSL-encrypted email
   SMTP Authentication: must be checked
   SMTP Encryption: must SSL
   SMTP username: websoft9smpt
   SMTP password: #fdfwwBJ8f    
   ```
2. Use SFTP to connect Cloud Server, then cd to */data/wwwroot/phabricator/phabricator* directory
3. Edit the file *mailers.json*, set the SMTP item for yourself, then save it
4. Run these commands
   ```
   # set smtp
   ./bin/config set --stdin cluster.mailers < mailers.json

   # restart service
   sudo systemctl restart phabricator-daemons
   ```
5. Setup completed

More SMTP Service(Gmail, Hotmail, QQ mail, Yahoo mail, SendGrid and so on)  settings or Issues with SMTP, please refer to Websoft9's *[SMTP Guide](https://support.websoft9.com/docs/faq/tech-smtp.html)*  

Phabricator have provided docs for you: [Configuring Outbound Email](https://secure.phabricator.com/book/phabricator/article/configuring_outbound_email/)

