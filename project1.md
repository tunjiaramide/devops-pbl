
### Updated the ubuntu and installed apache2
Setup EC2 instance on AWS and logged in <br/>
sudo apt install apache2

### Enabled firewall and allowed apache2
sudo ufw enable<br/>
sudo ufw allow "Apache"

### Accessed the ec2 IP on the browser
http://Public-IP-Address
  
### Installed and configured mysql server
sudo apt install mysql-server<br/>
sudo mysql_secure_installation

### Set up PHP with important depencies
sudo apt install php libapache2-mod-php php-mysql

### Configured a virtual host
sudo mkdir /var/www/projectlamp<br/>
sudo chown -R $USER:$USER /var/www/projectlamp<br/>
sudo vim /etc/apache2/sites-available/projectlamp.conf<br/>
Inserted virtual host config into the file<br/>
sudo a2ensite projectlamp<br/>
sudo a2dissite 000-default<br/>
sudo echo 'Hello LAMP from hostname' $(curl -s http://169.254.169.254/latest/meta-data/public-hostname) 'with public IP' $(curl -s http://169.254.169.254/latest/meta-data/public-ipv4) > /var/www/projectlamp/index.html<br/>
Testing on my browser

### Enabled webserver to serve PHP files
sudo vim /etc/apache2/mods-enabled/dir.conf<br/>
moved index.php to first




