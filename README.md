Before we start, we're going to be using the sudo command in the terminal. You'll need to use the password that you used to SSH into your server.


Step 1: Install apache2
```
  sudo apt-get install apache2
``` 
Step 2: Install mysql database
```
  sudo apt-get install mysql-server
```  
  You will be prompted for a password, default username will be root remember `your_password`
  
Step 3: Install PHP
```
  sudo apt-get install php7.0 php7.0-mysql libapache2-mod-php7.0 php7.0-cli php7.0-cgi php7.0-gd php-mysql
```  
Step 4: Install wordpress

  Navigate to the directory you want wordpress using
  ```
  cd /var/www/html/
  ```
  ```
  sudo wget -c http://wordpress.org/latest.tar.gz
  ```
  extract it using 
  ```
  sudo tar -xzvf latest.tar.gz
  ```
  Then remove the unnecessary file using
  
  ```
  sudo rm latest.tar.gz
  ```
  
Step 5: Change permissions

  You will need to use the username you have for SSH here
  
  
  ```
    sudo chown -R user:user /var/www/html/
   ``` 
   
   
Step 6: Create the wordpress database

  navigate to mysql with  
  ```
  mysql -u root -p 
  ```
  It will prompt you for the password you created earlier
  
  
  ```
    CREATE DATABASE wordpress;
  ```  
 
  ```
    FLUSH PRIVILEGES;
  ```
  
  ```
    EXIT;
  ```
    
 
Step 7: Config Wordpress
    
    Navigate to
    
    
    
    
    
   
    
   
   ` cd /var/www/html/wordpress/`
  
 
   ` mv wp-config-sample.php wp-config.php`
 
 

    `sudo nano wp-config.php`
 
 
      once in the config.php file, you'll need to change the following fields:
      
      
      
      
        define('DB_NAME', `'database_name_here'`); to `wordpress`
        
        
        define('DB_USER', `'wordpressuser'`); to `root`
        
        
        define('DB_PASSWORD', `'password'`); to `your_password`
        
        
        then ctrl-o to save, then ctrl-x to exit
        
        
        
 Step 8: Finish the installation in the browser
 
        Enter the IP of your server in the browser followed by /wordpress 
        
        For example: `127.0.0.1/wordpress`
        
        Enter your site name, admin username, a password and your email address, then click "Install Wordpress"
        
        You'll receive a confirmation, 
        
        sign in using your admin username and the password, and you're good to go!
   
