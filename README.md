# install-magento2-with-composer
Install Magento2 with Composer

# Install Composer
1.1) 	curl -sS https://getcomposer.org/installer | php 

1.2) 	sudo mv composer.phar /usr/local/bin/composer

# Create Magento 2 Dir
1.3) 	mkdir Magento2Dir; cd Magento2Dir

# Clone from GIT latest Branch {Make sure you put here the latest branch from repo}
2.1) 	git clone https://github.com/magento/magento2.git  --branch 2.1 .
# install all modules form composer
2.2) 	composer install
# install magento ( makesure to change DB & admin Credentials )
2.3) 
bin/magento setup:install --backend-frontname="EmizenTech" --db-host=localhost --db-name=emizentech_magento --db-user=magento2 --db-password=magento2password --base-url="http://yourmagento2.domain.com/" --currency="USD" --use-rewrites="1" --base-url-secure="http://yourmagento2.domain.com/" --admin-user="admin" --admin-password="EmizenTech@123!" --admin-email="info@emizentech.com" --admin-firstname="Emizen" --admin-lastname="Tech" 

#Clear Cache
2.4)  rm -rf var/cache/ var/di/ var/generation/ var/page_cache/

# Setup 
2.5) bin/magento setup:upgrade
# Deploy Static content
2.6)  bin/magento setup:static-content:deploy

# For Deploy Sample Data 
2.7) bin/magento sampledata:deploy
     bin/magento setup:upgrade
