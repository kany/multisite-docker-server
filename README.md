# Multisite Docker Server

[![Build Status](https://travis-ci.org/Justintime50/multisite-docker-server.svg?branch=master)](https://travis-ci.org/Justintime50/multisite-docker-server)
[![MIT Licence](https://badges.frapsoft.com/os/mit/mit.svg?v=103)](https://opensource.org/licenses/mit-license.php)

Quickly setup multiple websites via Docker containers on a single server.

## Usage
- **Traefik:** This project uses [Traefik](https://traefik.io) to load balance and route traffic to each site.
- **Static Sites:** Sites use `Nginx` to serve the files and `PHP` to interpret. You can replicate your own sites within each `site` folder.
- **MySQL:** Use this container if you'd like to run a database for your application. Alternatively, you can combine the contents of this docker-compose file with the docker-compose file of your site.

## Installation

1) Install [Docker](https://docker.com)
2) Navigate to each directory in this project and run `docker-compose up -d` **starting** with `Traefik`. 
Traefik can either host insecure content or SSL content. If using the SSL Traefik docker-compose command, each service will receive its own SSL certificate provided by `LetsEncrypt` through `Traefik`. Traefik will take care of automatically renewing these certs as well. Navigate to either the `/insecure` or `/ssl` directory based on your needs.
3) Start up each of your sites using `docker-compose up -d` in the directory of the site. Replicate the `site` folder structure as needed for other projects and update accordingly. Drop in your html/php files to each directory.

**NOTE:** If using the SSL Traefik config, you'll need to edit the `traefik.toml` file in that directory. There is a line to add your email and default domain. These will be used to register each SSL cert. Without this information, it won't run.

There you go! You have a fully functioning multisite Docker server running the latest versions of Nginx and PHP, each with their own SSL certificate - all automated and virtualized. Easily transfer your entire server to another machine, scale your services quickly, or share your projects with others. 
