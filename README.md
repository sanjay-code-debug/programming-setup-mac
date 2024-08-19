# programming-setup-mac
all types of services setup for mac OS 


## OS types for macbook







 ## Magento Setup For Macbook Pro (Normal Way)
      Services using brew(homebrew)
      -----------------------------
             sudo lsof -i -P | grep LISTEN   -- list all port
 
             - brew 
             - nginx
             - mysql
             - elasticSearch
             - openSearch
             - redis
             - rabbitMq
             - php
             - composer
             - beekeeper
             - phpStorm
             - varnish
             - xdebug
             - cs / md PSR


     Most Important Note for MAC(Disable | Kill From GUI | Launchpad ) : 
     ==================================================================

               ( If any Services is Not Starting | Not Able Install | Re-Installed Also | But That Services is Not Starting )


               - Issue with MAC (Launchedpad)

               - System Settings --> General ---> Login Items ---> Allow in Background  (You can see lists of Services is Running )

               - Remove from this GUI (click and select move to bin )
               - Disable by using the - password(system password)
               - Terminal Find that Service Port and Kill that Port

               - Finally Try to Re-install the Services It will Works like a Cham

        

                                 

             


 #### Brew (homebrew or brew)
 ---------------------------
     What Is : = 


     Install : = 

        - brew services list
        - brew update
        - brew cleanup
        - brew doctor

        - brew services start  service_name
        - brew services restart service_name
        - brew service stop service_name
        - brew install service_name
        - brew uninstall service_name

     Un-Install : = 

        - brew uninstall

     Path : = 

     Error : = 

     Any GUI location = 


 #### Nginx 
 -----------
     What Is : = 


     Install : = 

                brew install nginx
                


     Un-Install : = 

               brew uninstall nginx


     Path : = /opt/homebrew/etc/nginx

            - nginx.conf

            - /opt/homebrew/etc/nginx
            - cd server (create your .conf file for hosts configuration)

            

     Error : = 

     Any GUI location = 


 #### Apache2(httpd)
 --------------------
     What Is : = 


     Install : = 

                brew install httpd
                
     Un-Install : = 

               brew uninstall httpd

     Path : =  /opt/homebrew/etc/httpd

           cd /opt/homebrew/etc/httpd/extra
              nano httpd-vhosts.conf (add your configuration)

           nano /opt/homebrew/etc/httpd/httpd.conf  (here enable/include the file -  /opt/homebrew/etc/httpd/httpd.conf )
         
              

     Error : = 

     Any GUI location =      



#### Mysql
----------
     What Is : = 


     Install : = 

                brew install mysql@8.0

                brew services start mysql@8.0

                 mysql -u root (to connect first time) 

                /opt/homebrew/opt/mysql@8.0/bin/mysqld_safe --datadir\=/opt/homebrew/var/mysql :-: (if you don't want/need a background service you can just run)
                
                mysql_secure_installation  :-: (We've installed your MySQL database without a root password. To secure it run)

                echo 'export PATH="/opt/homebrew/opt/mysql@8.0/bin:$PATH"' >> ~/.zshrc   :-:  If you need to have mysql@8.0 first in your PATH, run:

                export LDFLAGS="-L/opt/homebrew/opt/mysql@8.0/lib"         | (For compilers to find mysql@8.0 you may need to set ) 
                export CPPFLAGS="-I/opt/homebrew/opt/mysql@8.0/include"    |


                brew services info mysql@8.0

                ps aux | grep mysqld   (On which port mysql is running)

                sudo lsof -i :3306  (mysql port) 

                sudo kill -9 <PID>  

                 cat /Users/sanjay.kumar/Library/LaunchAgents/homebrew.mxcl.mysql@8.0.plist


                 rm /Users/sanjay.kumar/Library/LaunchAgents/homebrew.mxcl.mysql@8.0.plist



     Un-Install : = 


     Path : = 

     Error : = 

     Any GUI location = 

     
    Issues : = 
         - when run - mysql_secure_installation we will get the error - Securing the MySQL server deployment. Error: Can't connect to local MySQL server through socket '/tmp/mysql.sock' (2)

         - Failure while executing; `/bin/launchctl bootstrap gui/503 /Users/sanjay.kumar/Library/LaunchAgents/homebrew.mxcl.mysql@8.0.plist` exited with 5. (check php is installed before mysql)


         - socket issue mysql

              - nano /opt/homebrew/etc/my.cnf  (check the socket )

                 - [client]
                   socket=/opt/homebrew/var/mysql/mysql.sock

                 -[mysqld]
                  socket=/opt/homebrew/var/mysql/mysql.sock   


                  

   
    Important CMD
    =============
                Take DB BackUp
                -------------
                       = mysqldump -u root -p database_name > database_backup_name.sql
                       
               Import DB
               -----------
                    use db_name;
                    source  import_db_name.sql;
                    
              Import Any Table to DB
              ----------------------
                   mysql -u root -p db_name < import_table_name.sql

#### MariaDB
------------
     What Is : = 


     Install : = 

              - brew install mariadb
              
              - brew services start mariadb

              - brew services stop mariadb

              - brew services restart mariadb
              
              - mariadb-secure-installation (issue -1)

              - sudo mysql
              - ALTER USER 'root'@'localhost' IDENTIFIED BY 'password';
              - FLUSH PRIVILEGES;

               


     Un-Install : = 

              - brew uninstall mariadb
              - brew uninstall mariadb@10.6 | x.y.z (versions)

              - rm -rf /opt/homebrew/etc/mecabrc

              - disable | remove for Login Items(system settings)



     Path : = 

     Error : = 

     Any GUI location = 

     
    Issues : = 
              1 - first time installation if want to go inside run (sudo mysql -enter (once enter set the password for root user) )
                - 

                - 

  
#### ElasticSearch
------------------
     What Is : = 


     Install : = 


     Un-Install : = 


     Path : = 

     Error : = 

     Any GUI location = 

     
    Issues : = 




#### OpenSearch
---------------
      What Is : = 


     Install : = 


     Un-Install : = 


     Path : = 

     Error : = 

     Any GUI location = 

     
    Issues : = 


#### MailHog
------------
      What Is : = 


     Install : = 

              brew install mailhog
              

     Un-Install : = 

              brew uninstall mailhog
              sudo rm -rf /opt/homebrew/Cellar/mailhog/1.0.1


     Path : = 

     Error : = 

     Any GUI location = 

     
    Issues : = 
  



#### Redis
----------
     What Is : = 


     Install : = 


     Un-Install : = 


     Path : = 

     Error : = 

     Any GUI location = 

     
    Issues : = 


#### RabbitMq
-------------
     What Is : = 


     Install : = 


     Un-Install : = 


     Path : = 

     Error : = 

     Any GUI location = 

     
    Issues : = 


#### PHP | PHP@8.0 | PHP@8.1 | PHP@7.4
--------------------------------------
     What Is : = 


     Install : = 

                  brew install php@8.1

                  brew info php@8.1

                  brew services restart php@8.1
                  
                  /opt/homebrew/etc/php/8.1/php.ini    = if want to modify the php.ini file location (to increase the memory_limit)

                  nano /opt/homebrew/etc/php/8.1/php-fpm.d/www.conf   (to modify the listen port)

                  


     Un-Install : = 

                  brew uninstall php@8.1

                  rm -rf /opt/homebrew/etc/php

                  rm -rf /opt/homebrew/etc/php-valet-bak1723803667
                  


     Path : = 

     Error : = /opt/homebrew/var/log

     Any GUI location = 

     
    Issues : = 

    - Failure while executing; `/bin/launchctl bootstrap gui/503 /Users/sanjay.kumar/Library/LaunchAgents/homebrew.mxcl.php@8.1.plist` exited with 5

    Memory limit issue (MAC)

          php -dmemory_limit=5G bin/magento setup:di:compile 
          php -dmemory_limit=5G bin/magento setup:static:content:deploy -f
    
         


#### Composer
-------------
     What Is : = 


     Install : = 


     Un-Install : = 


     Path : = 

     Error : = 

     Any GUI location = 

     
    Issues : = 

#### BeeKeeper
--------------


#### PhpStorm
-------------



#### Varnish
------------



#### Xdebuger
-------------
      What Is : = 


     Install : = 


     Un-Install : = 


     Path : = 

     Error : = 

     Any GUI location = 

     
    Issues : = 





#### PSR (CS | MD)
------------------
     What Is : = 


     Install : = 


     Un-Install : = 


     Path : = 

     Error : = 

     Any GUI location = 

     
    Issues : = 

 ## Magento Setup For Macbook Pro (valet-plus Way)


     Issues : = 

               1 - not able to install if    - composer and php is not available in your system.

               2 - sometime it is show error for root@localhost not having access using pass (YES / NO)  - go with MariaDB

               3 - some time composer global require weprovide/valet-plus  this command will not work so try to reset the path 

     Un-Install
     ===========

        - valet uninstall --force

        - composer global remove laravel/valet


     Install
     =======
         -  brew update
         -  brew doctor 

         - brew tap shivammathur/php
           brew install shivammathur/php/php@8.1
           brew link php@8.1 --force
           brew services restart php@8.1
           
             (or)

         - brew install php 
         - brew install php@8.1 
         - brew link php@8.1 --force
         

        - composer global require weprovide/valet-plus                      [global repo for valet-plus]
        
        - composer global config bin-dir --absolute (issue -3)              [to rebase the path for valet-plus]

         export PATH="$HOME/.composer/vendor/bin:$PATH"                     [just add for envvironment support]

         echo 'export PATH="$HOME/.composer/vendor/bin:$PATH"' >> ~/.zshrc  [just add for envvironment support]

         source ~/.zshrc  [reload the mac core file]

        - valet-plus install

        -  Homebrew PHP appears not to be linked. Please run [valet use php@X.Y]  

                - valet use php@8.1

        -  Brew was unable to install [mysql@5.7].

                   - valet use mariadb@10.6
                   - valet-plus install --with-mariadb
                   

        - * valet-plus install (default: installs mysql 5.7)
          * valet-plus install --with-mysql80 (installs mysql 8.0)
          * valet-plus install --with-mysql81 (installs mysql 8.1)
          * valet-plus install --with-mariadb (installs mariadb) (issue - 2)


    For Magento   
    ============

             - /Users/sanjay.kumar/Sites/forevernew    (my magento folder location)

             - cd /Users/sanjay.kumar/Sites

                           - valet park 

            - cd /forevernew
            
                          -  valet link forevernew   (link the project with valet)

           - valet  link dev.forevernew.co.nz --secure   (link the domain)  ( here magento domain name :- dev.forevernew.co.nz)

           - update the core_config_data table with the domain name  = http://dev.forevernew.co.nz.test    (.test is added to domain in table )

           - valet start

           - valet stop

           - valet status
                           

    



    



         
