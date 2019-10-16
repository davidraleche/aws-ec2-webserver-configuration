


Refer to 
```
 https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_Tutorials.WebServerDB.CreateWebServer.html
```


### Activate httaccess
    <Directory /var/www/xxxx>
        Options Indexes FollowSymLinks MultiViews
        AllowOverride All
        Require all granted
    </Directory>

### Proper Directory and file permission
    Directories 775
    Files 664

### Unix command for directories
```
find /desired_location -type d -print0 | xargs -0 chmod 0755
```

### Unix command for files
```
find /desired_location -type f -print0 | xargs -0 chmod 0644
```



### Create instance ec2 with ssh access

(1) create ec2 instance

(2) create vpc
Make usre to have public IPV4 dns 

    Get your VPC ID from your EC2 dashboard.
    Go to VPC dashboard. Select your VPC with VPC ID.
    Click on Actions and Select "Edit DNS Hostnames".
    Select Yes and click Save.

Now you can find Public DNS IPv4 value in EC2 dashboard.


(3) create subnet - 172.30.3.0/24 250 available ip addresses
make sure auto-assign IPV 4

(4) create internet gateway 

(5) create route tables - 
ADD 0.0.0.0/0 to internet gateway



### Install without verification
yum update -y


### apache web server
        <VirtualHost *:80>
          DocumentRoot "/www/docs/host.example.com"
          ServerName ec2-3-88-63-157.compute-1.amazonaws.comm
          ErrorLog "logs/host.example.com-error_log"
          TransferLog "logs/host.example.com-access_log"
        </VirtualHost>


### SSL
        wget https://dl.eff.org/certbot-auto


    user@webserver:~$ wget https://dl.eff.org/certbot-auto
    user@webserver:~$ sudo mv certbot-auto /usr/local/bin/certbot-auto
    user@webserver:~$ sudo chown root /usr/local/bin/certbot-auto
    user@webserver:~$ chmod 0755 /usr/local/bin/certbot-auto
    user@webserver:~$ /usr/local/bin/certbot-auto --help

    /usr/local/bin/certbot-auto --debug --apache certonly -d raleche.com

### Install new php package
```
sudo amazon-linux-extras install -y lamp-mariadb10.2-php7.2 php7.2
sudo amazon-linux-extras enable php7.3
sudo yum -y install php-cli php-pdo php-fpm php-json php-mysqlnd
```



### Start the Apache web server.

[ec2-user ~]$ sudo systemctl start httpd

### Use the systemctl command to configure the Apache web server to start at each system boot.

[ec2-user ~]$ sudo systemctl enable httpd

### You can verify that httpd is on by running the following command:

[ec2-user ~]$ sudo systemctl is-enabled httpd



```
To ensure that all of your software packages are up to date, perform a quick software update on your instance. This process may take a few minutes, but it is important to make sure that you have the latest security updates and bug fixes.

The -y option installs the updates without asking for confirmation. If you would like to examine the updates before installing, you can omit this option.

[ec2-user ~]$ sudo yum update -y

Install the lamp-mariadb10.2-php7.2 and php7.2 Amazon Linux Extras repositories to get the latest versions of the LAMP MariaDB and PHP packages for Amazon Linux 2.

[ec2-user ~]$ sudo amazon-linux-extras install -y lamp-mariadb10.2-php7.2 php7.2
```
