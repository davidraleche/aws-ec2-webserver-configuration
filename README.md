
Refer to 
https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_Tutorials.WebServerDB.CreateWebServer.html

### Create instance ec2 with ssh access

(1) create ec2 instance

(2) create vpc

(3) create subnet - 172.30.3.0/24 250 available ip addresses

(4) create internet gateway 

(5) create route tables - 0.0.0.0/0 to internet gateway



### Install without verification
yum update -y


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
