KEYCLOAK
========

Variables
---------
```
TZ 
KEYCLOAK_USER 
KEYCLOAK_PASSWORD
KEYCLOAK_DB 
KEYCLOAK_DB_USER
KEYCLOAK_DB_PASS
KEYCLOAK_URL
MYSQL_ROOT_PASS
```


SetUp
-----

```
cp .env.sample .env
```

```
docker-compose --compatibility up -d
```


Plugins
-------

### Gitlab
```
git clone https://github.com/Apicurio/apicurio-keycloak-extensions.git
```
```
docker run -it --rm -v $PWD/apicurio-keycloak-extensions:/srv/ maven:alpine bash
cd /srv && mvn package
```
```
docker cp apicurio-keycloak-extensions/social/target/apicurio-keycloak-extensions-social-*-SNAPSHOT.jar keycloak:/opt/jboss/keycloak/standalone/deployments/
```
