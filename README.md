docker-registry-nginx
=====================

A simple way of setting up [docker-registry] (2.0) behind a nginx reverse proxy using docker-compose.

Install:

1. Install docker-compose
2. Install Apache utils

```
sudo apt-get install apache2-utils
```
3. Create basic authentication
```
sudo htpasswd -c nginx/.htpasswd exampleuser
```

You can secure docker-registry perfectly yourself: https://github.com/docker/distribution/blob/master/docs/deploying.md

The nginx config files are based on https://github.com/docker/distribution/tree/release/2.0/contrib/compose/nginx

For more inspiration, check out this post [http://www.kf-interactive.com/blog/roll-your-own-docker-registry-with-docker-compose-supervisor-and-nginx/]
by [https://twitter.com/acidrain]

[docker-registry] https://github.com/docker/distribution#more-about-registry-20
