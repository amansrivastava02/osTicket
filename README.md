# osTicket
Installation of osTicket
Installation Of OS Ticket on Ubuntu
Start by updating packages on your system to the latest release.

sudo apt update


Step 2: Install and Configure MySQL / MariaDB database
We will need one MySQL database with a valid user, password, and hostname handy during installation. MySQL user specified need to have FULL privileges on the database created., we can also run the commands below to install mariadb from OS APT repositories:


Secure your DB Server:
#sudo mysql_secure_installation
After the MariaDB/MySQL server has been installed, proceed to create a database for osTicket. Login to your database server as root user and create a database for osTicket:

After the MariaDB/MySQL server has been installed, proceed to create a database for osTicket. Login to your database server as root user and create a database for osTicket


Step 3: Installing Apache on Ubuntu system
On Ubuntu, we can install Apache Web server from the official apt repository:
#sudo apt install apache2 -y

To start the service manually, run:
#sudo systemctl start apache2
Though the service is enabled to start on boot by default, manually allowing it you have to run:
#sudo systemctl enable apache2


#sudo apt install lsb-release ca-certificates apt-transport-https software-properties-common -y





Step 4: Install PHP and required extensions
Add PHP ppa:ondrej repository to your system:
#sudo apt update sudo apt install lsb-release ca-certificates apt-transport-https software-properties-common -y 


#sudo add-apt-repository ppa:ondrej/php



The next step is the to install PHP 8.0 on Ubuntu and required extensions:
#sudo apt update sudo apt install php8.0 php8.0-common -y 



#sudo apt install php8.0-imap php8.0-apcu php8.0-intl php8.0-cgi php8.0-mb

$php -v

Step 5: Download and Install osTicket
At this point, we should be ready to download the latest zip file of osTicket. Then uncompress the files and place a directory of your choice on the server web document root.
Install tools needed for downloading the software:
#sudo apt install curl wget unzip -y








Download latest release of osTicket:
#curl -s https://api.github.com/repos/osTicket/osTicket/releases/latest|grep browser_download_url| cut -d '"' -f 4 | wget -i -


Extract downloaded archive:
#unzip osTicket-v*.zip -d osTicket


You will get two directories after extraction: scripts and upload


Create a web directory for osTicket and mv these directories to it.
#sudo mv osTicket /var/www/




Next  create an osTicket configuration file:
#cd /var/www/osTicket/upload/include
 #sudo cp ost-sampleconfig.php ost-config.php
Change ownership of osTicket web directory to userwww-data and group.
#sudo chown -R www-data:www-data /var/www/
Disable default Apache webpage:
#sudo a2dissite 000-default.conf


Step 6: Configure Apache Web Server
Create VirtualHost configuration file for osTicket on Apache configurations directory:
#sudo vim /etc/apache2/sites-available/osticket.conf






#systemctl status apache2











http://10.180.16.155/setup/install.php






ISSUE/ERROR FACING WHILE INSTALLATION OF OsTicket












