FROM nginx:1.7

COPY nginx.conf /etc/nginx/nginx.conf
COPY .htpasswd /etc/nginx/.htpasswd
RUN chmod 644 /etc/nginx/.htpasswd

COPY my_certificate_bundle.crt /etc/ssl/certs/my_certificate_bundle.crt
COPY my_certificate.key /etc/ssl/certs/my_certificate.key
