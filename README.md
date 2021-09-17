# Develop Magneto with Docker

## Requirements

- Docker ([installed rootless](https://docs.docker.com/engine/security/rootless/))
- Docker Compose

## Useful Docker Commands

```
docker-compose up -d
docker-compose stop
docker-compose down
docker-compose exec <container-name> /bin/bash
```

## Magento installation

```
docker-compose exec php /bin/bash

cd /src

composer create-project --repository-url=https://repo.magento.com/ magento/project-community-edition .

bin/magento setup:install \
--base-url=http://localhost:8080/ \
--db-host=db \
--db-name=magento \
--db-user=magentouser \
--db-password=111111 \
--admin-firstname=admin \
--admin-lastname=admin \
--admin-email=admin@admin.com \
--admin-user=admin \
--admin-password=FRE#fre3 \
--language=pl_PL \
--currency=PLN \
--timezone=Europe/Warsaw \
--use-rewrites=1 \
--elasticsearch-host=elasticsearch \
--elasticsearch-port=9200
```
