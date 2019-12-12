Step 1: Install apache2
  sudo apt-get install apache2
  
Step 2: Install mysql database
  sudo apt-get install mysql-server
  You will be prompted for a password, default username will be root
  
Step 3: Install PHP
  sudo apt-get install php7.0 php7.0-mysql libapache2-mod-php7.0 php7.0-cli php7.0-cgi php7.0-gd
  
Step 4: Install wordpress
  Navigate to the directory you want wordpress using - cd /var/www/html/
    sudo wget -c http://wordpress.org/latest.tar.gz
  extract it using - sudo tar -xzvf latest.tar.gz
  
Step 5: Change permissions
  You will need to use the username you have for SSH here
    sudo chown -R user:user /var/www/html/
    
Step 6: Create the wordpress database
  navigate to mysql with - mysql -u root -p // It will prompt you for the password you created earlier
  
    CREATE DATABASE wordpress;
    GRANT ALL PRIVILEGES ON wordpress.* TO 'your_username'@'localhost' IDENTIFIED BY 'your_password';
    FLUSH PRIVILEGES;
    EXIT;
    
 
Step 7: Config Wordpress
  
    mv wp-config-sample.php wp-config.php
    nano wp-config.php
    
      once in the config.php file, you'll need to change the following fields:
      
        define('DB_NAME', 'database_name_here'); to 
   
