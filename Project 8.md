# CONFIGURE APACHE AS A LOAD BALANCER

Create an ubuntu ec2 instance with tcp port 80 open

Update Ubuntu 

`sudo apt update`

![](images/1.png)

Install Apache

`sudo apt install apache2 -y`

![](images/2.png)

`sudo apt-get install libxml2-dev`

![](images/3.png)

Enable modules

`sudo a2enmod rewrite`

`sudo a2enmod proxy`

`sudo a2enmod proxy_balancer`

`sudo a2enmod proxy_http`

`sudo a2enmod headers`

`sudo a2enmod lbmethod_bytraffic`

Restart Apache

![](images/4.png)

![](images/5.png)

Check apache's status

![](images/6.png)

Configure load-balancing

`sudo vi /etc/apache2/sitees-available/000-default.conf`

Add below configurations

![](images/7.png)

Restart Apache server

`sudo systemctl restart apache2`

Verify that our configuration works 

![](images/13.png)

Check logs of load-balancer access on webservers 

`sudo tail -f /var/log/httpd/access_log`

![](images/8.png)

![](images/14.png)