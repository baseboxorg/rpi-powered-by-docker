# rpi-powered-by-docker
Arch Linux ARM setup script to obtain a full RPI with Automatic Reverse Proxy without pain

## Stack
- IPv4/IPv6 support ( Dual Stack )
- [Git](https://git-scm.com/)
- [Docker](https://www.docker.com/)
- [talmai/rpi-watchtower](https://hub.docker.com/r/talmai/rpi-watchtower) as the Docker auto-update manager
- [braingamer/nginx-proxy-arm](https://hub.docker.com/r/braingamer/nginx-proxy-arm/) as Reverse Proxy
- [hermanzdosilovic/rpi-docker-letsencrypt-nginx-proxy-companion](https://hub.docker.com/r/hermanzdosilovic/rpi-docker-letsencrypt-nginx-proxy-companion/) as automatic Let's Encrypt provisioner ( official companion docker for braingamer/nginx-proxy-arm )
- [apache-nginx-referral-spam-blacklist](https://github.com/Stevie-Ray/apache-nginx-referral-spam-blacklist) preloaded for every host

## Modules
- [UI for Docker](https://github.com/kevana/ui-for-docker) ( [ui_for_docker.sh](modules/ui_for_docker.sh) )
- [Portainer](https://github.com/portainer/portainer) ( [portainer.sh](modules/portainer.sh) )
- [DNS Server](https://github.com/julianxhokaxhiu/docker-powerdns) ( [dns_server.sh](modules/dns_server.sh) )

## Requirements
A clean Arch Linux ARM install with SSH capability as root user ( or any user which has sudo powers ).

## Installation
```bash
wget https://github.com/julianxhokaxhiu/rpi-powered-by-docker/archive/master.zip
unzip master.zip && cd rpi-powered-by-docker-master
find ./ -name "*.sh" -exec chmod +x {} \;
./install.sh
```

## Module setup
Edit the configuration variables to fit your needs, inside every module, then
```bash
./modules/<module_name>.sh
# example ./modules/dns_server.sh
```

## Disclaimer
- The mapping of the domains to the Host IP is considered done already externally to this project ( through DNS Server or statically inside your `hosts` file )
