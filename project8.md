## **Documentation for Project 8** 

### Apache Load Balancer Installation and Enabling Module

`sudo apt update`
`sudo apt install apache2 -y`
`sudo apt-get install libxml2-dev`
`sudo a2enmod rewrite`
`sudo a2enmod proxy`
`sudo a2enmod proxy_balancer`
`sudo a2enmod proxy_http`
`sudo a2enmod headers`
`sudo a2enmod lbmethod_bytraffic`

![Enabling-Module-and-installing-apache-loadbalancer](./Images/update.png)
![Enabling-Module-and-installing-apache-loadbalancer](./Images/install-apache.png)
![Enabling-Module-and-installing-apache-loadbalancer](./Images/installing-libraries.png)
![Enabling-Module-and-installing-apache-loadbalancer](./Images/enabling-lb-modules.png)
![Enabling-Module-and-installing-apache-loadbalancer](./Images/enabling-lb-modules&apache-status.png)

### Apache status verified as running

`sudo systemctl restart apache2`
`sudo systemctl status apache2`

![Apache-up-and-running](./Images/apache-up&running.png)

### Configuring Load Balancer

`sudo vi /etc/apache2/sites-available/000-default.conf`
![Load-Balancer-config](./Images/lb-configure.png)

### Confirming even distribution of traffic by load Balancer

### HTTP get request logged in webserver 1 log file

`sudo tail -f /var/log/httpd/access_log`

![log-record-after-several-refresh-for-Webserver 1](./Images/log.png)

### HTTP get request logged in webserver 2 log file

`sudo tail -f /var/log/httpd/access_log`

![log-record-after-several-refresh-for-Webserver 2](./Images/log1.png)

### Local DNS Names Resolution Configuration

`sudo vi /etc/apache2/sites-available/000-default.conf`

![updating-Lb-config-file-with-the-arbitrary-names](./Images/local-dns.png)

### Curling our webservers for access locally by our webservers

`curl http://Web1`
`curl http://Web2`

![accessing-our-webservers-locally-from-load-balancer](./Images/page-loaded.png)

![accessing-our-webservers-locally-from-load-balancer](./Images/curl-web.png)