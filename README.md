# docker-reverse-proxy
Docker setup for reverse proxy server using the `jwilder/nginx-proxy` container. Additional the `JrCs/docker-letsencrypt-nginx-proxy-companion` container will automatically issue https certificates for the virtual hosts.

* https://github.com/jwilder/nginx-proxy
* https://github.com/JrCs/docker-letsencrypt-nginx-proxy-companion


## Setup

create the following directories:

```bash
$ mkdir /srv/nginx/certs
$ mkdir /srv/nginx/vhost.d
$ mkdir /srv/nginx/html
```

## Start

Execute the docker-compose file

```bash
$ docker-compose up -d
```

## Usage

Whenever you create a new container that must be exposed to the internet, just add the hostname using an environment variable

```bash
$ docker run -e VIRTUAL_HOST=foo.bar.com  ...
```
To add the lets-encrypt support, add the following environment variables as well:

```
LETSENCRYPT_HOST: example.com
LETSENCRYPT_EMAIL: contact@example.com
```
