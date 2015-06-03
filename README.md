# docker-registry-nginx

A simple way of setting up [docker-registry] v2 behind a nginx reverse proxy using docker-compose.

## Why?
I want to secure my docker registry with tools I already know, like nginx, which provides for IP restrictions,
Basic access authentication and TLS.

## Other options
You can secure docker-registry perfectly yourself, as described in the [documentation].

Also check out this excellent post, [Roll your own Docker registry] by [Philipp Wintermantel] at [KF Interactive].

## Install

### docker-compose
Check the [official documentation] to install docker-compose.

### Apache utils
Apache utils provides the `htpasswd` tool to generate .htpassword files.
Install it on Ubuntu like this:

```
sudo apt-get install apache2-utils
```

### Generate a .htpasswd file
In order to create a .htpasswd file run this command:

```
htpasswd -c nginx/.htpasswd exampleuser
```

You will be prompted for a password.

### Add certificates
Create a self-signed certificate or add your existing certificates to the `nginx` directory and update the `Dockerfile` accordingly.

## Disclaimer
* The nginx config files were copied and adapted from the [registry project source code].

* Basic authentication only works when TLS/SSL is enabled.

[docker-registry]: https://github.com/docker/distribution#more-about-registry-20
[Roll your own Docker registry]: http://www.kf-interactive.com/blog/roll-your-own-docker-registry-with-docker-compose-supervisor-and-nginx/
[Philipp Wintermantel]: https://twitter.com/acidrain
[documentation]: https://github.com/docker/distribution/blob/master/docs/deploying.md
[registry project source code]: https://github.com/docker/distribution/tree/release/2.0/contrib/compose/nginx
[KF Interactive]: http://www.kf-interactive.com/
[official documentation]: https://docs.docker.com/compose/install/
