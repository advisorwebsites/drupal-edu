# Drupal Education

This is a starter guide that you will use to set up a Drupal playground on your computer.

## Part 1 - Dependencies

- Install Homebrew: https://brew.sh/

- Install dependencies: `brew install php@7.1 apache2 mariadb`

- Turn on apache and mariadb: `brew services restart httpd && brew services restart mariadb`

- Replace your Apache config (httpd.conf with the one attached to this repo. (Find my name "lucasrasmussen" and replace with your own user folder (and location if preferred).

- Download Drupal: `composer create-project drupal-composer/drupal-project:8.x-dev ~/Sites/Drupal --no-interaction` (Change the second parameter appropriately if you altered the apache config)

- Log into mariadb(mysql) to create your user `mysql -uroot`
- Create a user called drupal with the password drupal (This isn't secure, but who cares, sandboxes are dirty AF) `CREATE USER 'drupal'@'localhost' IDENTIFIED BY 'drupal';`
- Create a database called drupal. ```CREATE DATABASE `drupal`;``` (Yes, so many tildes, I'm sorry ok?)
- Lets make our lives easy and grant lots of priveleges (Let's remember we're still being insecure, but it doesn't matter) `GRANT USAGE ON *.* TO 'drupal'@localhost IDENTIFIED BY 'drupal';` then `GRANT ALL privileges ON `drupal`.* TO 'drupal'@localhost;` and then just to finish this off `FLUSH PRIVILEGES;`

## Part 2 - Install Drupal

- Go to `localhost:8080` in the browser.

- For this game, we'll be using the Umami profile.

- Enter the database information you entered previously, unless you changed anything, that's drupal:drupal for database drupal. 

- Proceed through the rest of installation.
