# dockerstack-nextcloud
Quick and simple Nexcloud instance on Docker (using nextcloud fpm &amp; mariadb) with defined volumes


## Note: This requires you to have a reverse proxy in place already

When using the FPM image you need another container that acts as web server on port 80 and proxies the requests to the Nextcloud container. In this example a simple nginx container is combined with the Nextcloud-fpm image and a MariaDB database container. The data is stored in docker volumes. The nginx container also need access to static files from your Nextcloud installation. It gets access to all the volumes mounted to Nextcloud via the volumes_from option.The configuration for nginx is stored in the configuration file nginx.conf, that is mounted into the container.

As this setup does not include encryption it should to be run behind a proxy.
Make sure to set the variables MYSQL_ROOT_PASSWORD and MYSQL_PASSWORD before you run this setup.
