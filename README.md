# Opencart deployment on domain

This project deploys the OpenCart project by Bitnami and assumes that it runs behind a reverse proxy with preconfigured SSL certificate.

```plaintext
git clone git@github.com:andriesh/opencart-ssl.git
cd opencart-ssl
```

Change the domain variable `OPENCART_HOST` in your `docker-compose.yml` file to your real domain.

Then bring up the project:

```plaintext
docker compose up -d
```

Fixing the SSL URLs by applying a fix:

```plaintext
docker exec -it opencart-ssl-opencart-1 sed -i 's/http:/https:/g' /bitnami/opencart/config.php
docker exec -it opencart-ssl-opencart-1 sed -i 's/http:/https:/g' /bitnami/opencart/administration/config.php
```
