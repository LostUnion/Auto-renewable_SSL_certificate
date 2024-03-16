# Auto-renewable SSL certificate

🔒 In order to be able to use telegram bots or just have a secure connection on the server, an SSL certificate is required that changes the HTTP protocol to HTTPS. This guide will use an auto-renewable SSL certificate from [Let's Encrypt](https://letsencrypt.org).

### 🤖 To install an SSL certificate, you need to install and run certbot..
In order to install certbot, use the following command:

```bash
sudo apt install certbot python3-certbot-nginx
```
Using the following command, Certbot reads addresses from the configuration file located at the path /etc/nginx/sites-available/config, and installs an SSL certificate for all addresses that are in it.

```bash
sudo certbot --nginx -d [config file] --register-unsafely-without-email
```
*Add a postscript --register-unsafe-without-email if you do not want to enter your email.*

### It's done! The certificate will be valid for 3 months, after which it will be automatically updated.