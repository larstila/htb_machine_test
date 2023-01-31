# Server setup

Steps:

1. Download

 ```ubuntu-22.10-live-server-amd64```

5. Setting it up on VM VirtualBox Manager with settings[^1]

3. Server name valo, emma:changeme

4. Install Apache2

`sudo apt-get update \
sudo apt-get install apache2 \
sudo service apache2 restart \
`
5. Installed net-tools

`sudo apt-get install net-tools`

6. Allow firewall 

`sudo ufw allow in "Apache"` \
`sudo ufw allow in ssh`

Now with VM port forwarding and Ubuntu ufw allowing I can acces the machine and website from my host. 

7. Install MYSQL

`sudo apt install mysql-server`

8. Install PHP

`sudo apt install php libapache2-mod-php php-mysql`

9. Creating a Virtual Host

```
sudo mkdir /var/www/valo
sudo chown -R $USER:$USER /var/www/valo
sudo nano /etc/apache2/sites-available/valo.conf
``` 

With this following VirtualHost configuration, we’re telling Apache to serve valo using /var/www/valo as the web root directory.

```
<VirtualHost *:80>
    ServerName valo
    ServerAlias www.valo
    ServerAdmin webmaster@localhost
    DocumentRoot /var/www/valo
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```

10. Using a2ensite to enable the new virtual host

`sudo a2ensite valo`

Disable the default and restart

```
sudo a2dissite 000-default
sudo systemctl reload apache2
```


[^1]:
![kuva](https://user-images.githubusercontent.com/61313043/215742575-81417a2f-c6f8-4c57-86d9-72ec6c47f595.png)
