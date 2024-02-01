# Nextcloud on Raspberry PI

This is a boilerplate for a docker-based Nextcloud instance, living behind Traefik proxy. I needed to install it on my Raspberry PI 4. It should work on any debian server actually.

- clone the repo to the pi (e.g. into your home directory)
- ensure you have docker up & running on your system (`docker run hello-world`)
- create & populate `.env` using the `.env.example` provided
- run `init.sh` for some basic setup
- update email address for let's encrypt in `./traefik/traefik.yml`
- create proxy network (`sudo docker network create proxy-network` -> needs to match what's in `docker-compose.yml`)
- run `sudo docker compose up -d`
- visit the configured domain and start installation (it needs to be pointing to your PI with fixed IP address)

# Nextcloud configuration

After successful installation it makes sense to configure some typical NC stuff:

File: `./nextcloud-data/config/config.php`

```
  'trusted_domains' => 
  array (
    0 => 'domain.ltd',
  ),

  'overwrite.cli.url' => 'https://domain.ltd',
  'overwriteprotocol' => 'https',
```