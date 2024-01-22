# racikan docker compose apache2, php5.6, mariadb, phpmyadmin
tambah folder www untuk menempatkan folder project

# single run container
docker run -d --restart=always --name coba-php  -p 8555:80 php:5.6-apache

# menghubungkan container dengan network lain nya
docker network connect {network_yang_dituju} {container_yang_akan_dihubungkan}

# docker ps with ip address
docker ps -q | xargs -n 1 docker inspect --format '{{ .Name }} {{range .NetworkSettings.Networks}} {{.IPAddress}}{{end}}' | sed 's#^/##';
