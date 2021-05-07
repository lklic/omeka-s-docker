# Omeka S dockerized with NGINX, Let's Encrypt Proxies, and automated backups

[![GitHub license](https://img.shields.io/github/license/maehr/omeka-s-docker.svg)](https://github.com/maehr/omeka-s-docker/blob/master/LICENSE.md)

## Installation

Install [Docker](https://www.docker.com/).

Set up NGINX and LetsEncrypt proxy containers using this github project:
https://github.com/evertramos/nginx-proxy-automation


edit .env variables and rename
```bash
mv example.env .env
```

make setup.sh executable
```bash
chmod +x setup.sh
```

Export environment variables and use `setup.sh` to create `database.ini` and set permissions

```bash
sudo ./setup.sh
```
## Usage

Start Omeka S

```bash
docker-compose up -d
```

If your installation complains about not being able to write to the folder `files`, fix permissions accordingly.

```bash
cd example
chown -R www-data:www-data files logs modules themes
```

Stop Omeka S

```bash
docker-compose down
```

Backup of DB is documented here:
https://github.com/zeenlym/docker-mariadb-backup
