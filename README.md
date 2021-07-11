# Setup steps

Magento2.4.2 project setup with sample data

Setup Step
-  You should need to be installed following before setup project on your device
    - PHP 7.4
    - Elastic search
    - composer install on your device

- Run below commands

  `git clone git@github.com:chathurajanaka/magentotest.git`

  `composer install`


- Run below command in terminal

  `find var generated vendor pub/static pub/media app/etc -type f -exec chmod g+w {} +`

  `find var generated vendor pub/static pub/media app/etc -type d -exec chmod g+ws {} +`

  `sudo chown -R :www-data .`

  `sudo chmod u+x bin/magento `


- If you are  in localhost, then Open hosts file and add your

  `sudo vi  /etc/host`

  `127.0.1.1 www.magento24.com`


- If you are  in localhost, then Create  nginx Virtual Hosts


- Import database
  

- Run below command with all parameters(Please change base url,database name,user and password)


`bin/magento setup:install \--base-url=http://www.magento24.com --db-host=localhost --db-name=magento24 --db-user=admin --db-password=admin123 --backend-frontname=admin --admin-firstname=Chathura --admin-lastname=Janaka --admin-email=useremail@gmail.com --admin-user=newuser --admin-password=newuser@123 --language=en_US --currency=USD --timezone=America/Chicago --use-rewrites=1 `



- Run below commands

  `sudo rm -rf var/view_preprocessed/ pub/static/frontend/ pub/static/adminhtml var/cache/ generated/`

  `php bin/magento setup:upgrade`

  `php bin/magento setup:di:compile`

  `php bin/magento setup:static-content:deploy -f`
