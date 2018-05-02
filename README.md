This is a docker implementation of [Globaleaks](https://www.globaleaks.org/).

It is [available on DockerHub](https://hub.docker.com/r/transparencyfinland/globaleaks/).

Here is a minimal `docker-compose.yml` needed to run this image:

```yaml
version: "3"
services:
  globaleaks:
    image: transparencyfinland/globaleaks
    build: .
    cap_add:
      - NET_ADMIN
    ports:
      - 80:80
      - 443:443
    volumes:
      - ./data/var/:/var/globaleaks

``` 

Here is a oneliner for `docker`:  Actually, I use `docker-compose` and am not going to bother looking this up.  Submit a pull request.

This container does not stop gracefully, probably because of the docker-entrypoint.sh stuff going on. 

## Notes: 
 Based on work by @ckeeney

## Installation: 
Install by cloning this repo, and run sudo docker-compose up

