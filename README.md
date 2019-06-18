# multisite-docker-server
Quickly setup multiple websites via Docker containers.

## Usage
This project uses `Traefik` to load balance and route traffic to each site.

Sites use `Nginx` to serve the files and `PHP` to interpret.

Each of the above services have their own Docker containers.

<hr>

To setup the server, simply:

- 1) Install Docker
- 2) Navigate to each directory in this project and run `docker-compose up -d` starting with `Traefik` followed by however many other sites you'd like to run.
- 3) There you go! You have a fully functioning multisite Docker server running the latest versions of Nginx and PHP.