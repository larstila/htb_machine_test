#Server setup

Steps:

1. Downloaded ```ubuntu-22.10-live-server-amd64```
2. Setting it up on VM VirtualBox Manager with settings[^1]

3. Server name valo, emma:changeme

4. Install Apache2
`sudo apt-get update \
sudo apt-get install apache2 \
sudo service apache2 restart \
`
5. Istalled net-tools
`sudo apt-get install net-tools`

7. Allow firewall 
`sudo ufw allow in "Apache"`

5. Install PHP 


[^1]:
![kuva](https://user-images.githubusercontent.com/61313043/215742575-81417a2f-c6f8-4c57-86d9-72ec6c47f595.png)
