# Initial Installation

If you have completed the Phabricator deployment on Cloud Platform, the following steps is for you to start use it quikly

## Preparation

1. Get the **Internet IP** on your Cloud Platform
2. Check you **[Inbound of Security Group Rule](https://support.websoft9.com/docs/faq/tech-instance.html)** of Cloud Console to ensure the TCP:80 is allowed
3. Make a domain resolution on your DNS Console if you want to use domain for Phabricator

## Phabricator Installation Wizard

1. Using local Chrome or Firefox to visit the URL *http://domain name* or *http://Internet IP*, you will enter the register interface of Phabricator
  ![Phabricator create admin](https://libs.websoft9.com/Websoft9/DocsPicture/en/phabricator/phabricator-createadmin-websoft9.png)

2. There will be an "Unresolved Setup Issues" prompt on the top menu of the console. There are two initialization suggestions.
   ![Phabricator console](https://libs.websoft9.com/Websoft9/DocsPicture/en/phabricator/phabricator-dashboard-websoft9.png)

3. **Set the URI**. 
   ![Phabricator URI](https://libs.websoft9.com/Websoft9/DocsPicture/en/phabricator/phabricator-url-websoft9.png)

4. The system will generate a command to set the URL, copy the command, and then SSH remote login to the server to run the it
   ![Phabricator URI Command](https://libs.websoft9.com/Websoft9/DocsPicture/en/phabricator/phabricator-urlcmd-websoft9.png)

5. **Set Authentication**. Open the **No Authentication Providers Configured** from: **Config** > **SETUP** > **Setup Issues**
   ![Phabricator Authentication](https://libs.websoft9.com/Websoft9/DocsPicture/en/phabricator/phabricator-setautho-websoft9.png)

> More useful Phabricator guide, please refer to [Phabricator Documentation](https://secure.phabricator.com/book/phabricator/)

## Q&A

#### I can't visit the start page of Phabricator?

Your TCP:80 of Security Group Rules is not allowed so there no response from Chrome or Firefox

#### Which database does this Phabricator use?

MySQL
