# multisite-docker-server
Quickly setup multiple websites via Docker containers on a single server.

## Usage
- **Traefik:** This project uses `Traefik` to load balance and route traffic to each site.
- **Static Sites:** Sites use `Nginx` to serve the files and `PHP` to interpret. You can replicate your own sites within each `site` folder.
- **MySQL:** Use this container if you'd like to run a database for your application. Additionally, you can combine the contents of this docker-compose file with the docker-compose file of your site.

## Installation

1) Install Docker
2) Navigate to each directory in this project and run `docker-compose up -d` starting with `Traefik`. 
Traefik can either host insecure content or SSL content. If using the SSL Traefik docker-compose command, each service will receive its own SSL certificate provided by `LetsEncrypt` through `Traefik`. Traefik will take care of automatically renewing these certs as well. Navigate to either the `/insecure` or `/ssl` directory based on your needs.
3) Start up each of your sites using `docker-compose up -d`. Replicate the `site` folder structure as needed for other projects and update accordingly. Drop in your html/php files to each directory.

There you go! You have a fully functioning multisite Docker server running the latest versions of Nginx and PHP, each with their own SSL certificate - all automated and virtualized. Easily transfer your entire server to another machine, scale your server quickly, or share with others. 