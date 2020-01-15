<div align="center">

# Multisite Docker Server

Quickly setup multiple websites via Docker containers on a single server.

[![Build Status](https://travis-ci.org/Justintime50/multisite-docker-server.svg?branch=master)](https://travis-ci.org/Justintime50/multisite-docker-server)
[![MIT Licence](https://badges.frapsoft.com/os/mit/mit.svg?v=103)](https://opensource.org/licenses/mit-license.php)

<img src="assets/showcase.png">

</div>

## What Can it Do?

This project serves as the boilerplate to setting up a full Docker server for multiple sites or applications. You deserve to spend your time building cool apps and desiging sites, not configuring server infra.

- **Traefik:** This project uses [Traefik](https://traefik.io) to load balance and route traffic to each site.
- **Nginx/PHP Site:** Uses `Nginx` to serve files and `PHP` to interpret. You can replicate your own sites by copying and modifying this folder for as many sites as you have.
- **MySQL:** Use this container if you'd like to run a database for your application. Alternatively, you can combine the contents of this docker-compose file with the docker-compose file of your site.

## Usage

1) **Install Docker:** Once [Docker](https://docker.com) is installed, make sure to login.
2) **Start Traefik:** Navigate to the `Traefik` directory and run `docker-compose up -d` in either the `insecure` or `ssl` folder. Traefik can either host insecure content or SSL content. If using the SSL Traefik docker-compose command, each service will receive its own SSL certificate provided by `LetsEncrypt` through `Traefik`. Traefik will take care of automatically renewing these certs as well. Navigate to either the `/insecure` or `/ssl` directory based on your needs.
3) Start up each of your sites using `docker-compose up -d` in the directory of the site. Replicate the `site` folder structure as needed for other projects and update accordingly. Drop in your html/php files to each directory.

**NOTE:** If using the SSL Traefik config, you'll need to edit the `traefik.toml` file in that directory. There is a line to add your email and default domain. These will be used to register each SSL cert. Without this information, it won't run.

There you go! You have a fully functioning multisite Docker server running the latest versions of Nginx and PHP, each with their own SSL certificate - all automated and virtualized. Easily transfer your entire server to another machine, scale your services quickly, or share your projects with others. 
