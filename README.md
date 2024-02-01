# Nextcloud on Raspberry PI

This is a boilerplate for a docker-based Nextcloud instance, living behind Traefik proxy. I needed to install it on my Raspberry PI 4. It should work on any debian server actually.

- clone the repo to the pi (e.g. into your home directory)
- ensure you have docker up & running on your system (`docker run hello-world`)
- create & populate `.env` using the `.env.example` provided
- run `init.sh` for some basic setup
- run `sudo docker compose up -d`
- visit the configured domain and start installation (it needs to be pointing to your PI with fixed IP address)
