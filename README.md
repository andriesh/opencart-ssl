# Opencart deployment on domain

This project deploys the OpenCart project by Bitnami and assumes that it stands behind a reverse proxy with preconfigured SSL certificate.

```plaintext
git clone git@github.com:andriesh/opencart-ssl.git
cd opencart-ssl
docker compose up -d
```

```plaintext
docker exec -it opencart-ssl-opencart-1 sed 's/http:/https:/g' /bitnami/opencart/config.php
docker exec -it opencart-ssl-opencart-1 sed 's/http:/https:/g' /bitnami/opencart/administration/config.php
```
