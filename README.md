# aws-ec2-webserver




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
