---
apple-notes-id: 74C5ED49-461C-4872-B7B7-9D1C94ADBC15
---
<a href="https://docs.litespeedtech.com/cloud/images/rails/#__tabbed_1_8" rel="noopener" class="external-link" target="_blank"><u>https://docs.litespeedtech.com/cloud/images/rails/#__tabbed_1_8</u></a>
@Senha3231Jafk1986**#
77.37.69.194
Sim

[srv.casadoscn.com.br](http://srv.casadoscn.com.br)

/var/log/letsencrypt/letsencrypt.log

ruby 3.0.7p220

Rails 7.1.5

ufw allow from 192.0.2.0 to any port 7080

[api.casadoscn.com.br](http://api.casadoscn.com.br)



Welcome to One-Click OpenLiteSpeed Rails Server.
To keep this Droplet secure, the firewalld is enabled.
All ports are BLOCKED except 22 (SSH), 80 (HTTP) and 443 (HTTPS).

The Rails OLS One-Click Quickstart guide:
- https://docs.litespeedtech.com/cloud/images/rails/

In a web browser, you can view:
- The sample rails site: http://77.37.69.194/

Project location:
- /usr/local/lsws/Example/html/demo/

On the server:
- You can get the Web Admin admin password with the following command:
   sudo cat /home/ubuntu/.litespeed_password

System Status:
  Load : 0.00, 0.02, 0.16
  CPU  : 3.01224%
  RAM  : 527/15992MB (3.30%)
  Disk : 2/193GB (2%)


RewriteCond %{SERVER_PORT} 80
RewriteRule (.*) https://%{HTTP_HOST}%{REQUEST_URI} \[R=301,L\]


Vhost