# More

Each of the following solutions has been proven to be effective and We hope to be helpful to you.

## Domain binding

The precondition for binding a domain is that Phabricator can accessed by domain name.

Nonetheless, from the perspective of server security and subsequent maintenance considerations, the **Domain Binding** step cannot be omitted.

Phabricator domain name binding steps:

1. Connect your Cloud Server
2. Modify [Apache vhost configuration file](/stack-components.md#apache), change the **ServerName**'s value *www.example.com* to your domain name
   ```text
    <VirtualHost *:80>
    ServerName www.example.com
    ...
    </VirtualHost>
   ```
3. Save it and restart [Apache Service](/admin-services.md#apache)


## Other

Coming soon
