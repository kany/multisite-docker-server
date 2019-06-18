# multisite-docker-server
Quickly setup multiple websites via Docker containers on a single server.

## Usage
This project uses `Traefik` to load balance and route traffic to each site.

Sites use `Nginx` to serve the files and `PHP` to interpret.

Each of the above services have their own Docker containers.

## Installation

1) Install Docker
2) Navigate to each directory in this project and run `docker-compose up -d` starting with `Traefik` followed by however many other sites you'd like to run. Replicate the `site` folder structure as needed for other projects and update accordingly. Drop in your html/php files to each directory.
3) There you go! You have a fully functioning multisite Docker server running the latest versions of Nginx and PHP.