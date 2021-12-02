# NGINX / MYSQL / PHP for development with Docker-compose

This is a docker-compose LEMP stack for PHP web development which includes the following php extensions :

* mysqli
* pdo_mysql
* gd
* zip
* intl
* pcntl
* opcache
* exif
* mbstring

## Dependencies

* [Docker](https://www.docker.com/)
* [Docker Compose](https://docs.docker.com/compose/install/)

## How it works

### Download this repo

With git clone or download button

### Copy your source code into www folder

Create a 'www' folder and copy your source code into it or clone a repo into 'www' folder. Example with WordPress repository :

`git clone https://github.com/WordPress/WordPress www`

### Start the containers

For the first time, create the containers :

`docker-compose up -d`

If you have already created the containers you must to start the containers :

`docker-compose start`

After that you can visit http://localhost

### Access to PhpMyAdmin

Visit http://localhost:8080

### Permissions (optional)

If you have need to change permissions on the www folder :

`chmod -R 777 www`

Useful if PHP execution need to write in the folder (like WordPress installation).

### Change nginx config (optional)

If you need to modify the nginx configuration you can modify nginx/default.conf file.

### Change php config (optional)

If you need to modify the php configuration you can modify php/php.ini file.

### Database

* Host : mysql
* User : root
* Password : root
* Database name : project

#### Files backup

The files of the MySQL database in the container are mounted in the 'mysql/data' directory. This means that the database files are saved in the 'mysql/data' directory. If you remove the database container by accident, or do a `docker-compose rm`, you can do the `docker-compose up -d` command without affecting the information in the database.
