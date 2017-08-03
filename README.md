# Grand Concierge

Grand Concierge website with basic shopping cart in Drupal 8.


## Getting started

First, you have to install this on your computer:

- Brew [_website_](https://brew.sh)
```bash
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

- Unison
```bash
brew install unison
```

- Drush (Installed locally)
```bash
brew install drush
```

- PHP 5.6 o superior (Installed locally) [_Complete guide to setup your local environment_](https://getgrav.org/blog/macos-sierra-apache-multiple-php-versions)
```bash
brew tap homebrew/dupes
brew tap homebrew/versions
brew tap homebrew/php
brew update
brew install php56 --with-httpd24
```

- Composer
```bash
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
php -r "if (hash_file('SHA384', 'composer-setup.php') === '669656bab3166a7aff8a7506b8cb2d1c292f042046c5a994c43155c0be6190fa0355160742ab2e1c88d40d5be660b410') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
php composer-setup.php
php -r "unlink('composer-setup.php');"
mv composer.phar /usr/local/bin/composer
```

- Docker for Mac : https://www.docker.com/docker-mac :
[_download_](https://store.docker.com/editions/community/docker-ce-desktop-mac)

- Docker Sync
```bash
gem install docker-sync
```


## Initial configuration

- `git@github.com:georch/d8-basic-cart.git`
- `cd d8-basic-cart`
- `composer install`
- `./vendor/bin/project-x drupal:local-setup`



## Daily rutine

- Docker for Mac should be running and Apache and MySQL should be turned off locally `sudo apachectl graceful && mysql.server stop`
- `./vendor/bin/project-x engine:up` will start the docker containers for this project.
- `./vendor/bin/project-x engine:down` will stop the docker containers for this project.
- `git pull` to update your repository.
- `drush @local.d-basic-cart config-import` to import the default configuration.
- `drush @local.d-basic-cart config-export` to export to code the configuration changes.


## Install a module

- Use Composer to install new modules. For instance, to install Admin Toolbar module run `composer require drupal/admin_toolbar`
- Commit the changes applied to composer.json and composer.lock


## Log in to Drupal
- Go to http://local.concierge.com/user/login and use admin:admin
- Use Drush to create a temp login url `drush @local.d-basic-cart uli`
