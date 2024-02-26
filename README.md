# poc-superset-pentaho
Data analytics via pentaho and superset


### Installing Superset 

Option 1: Use Docker

```
sudo docker run -d -p 8080:8088 --name superset alexmerced/dremio-superset
docker exec -it superset superset init
sudo docker exec -it superset superset init
docker ps
```

http://localhost:8080/login/ with username admin and password admin



Option 2: Use docker-compose (not yet successful)

### Installing Postgres

sudo docker run -p 5432:5432 --name some-postgres2 -e POSTGRES_PASSWORD=mysecretpassword -d postgres 

Allow firewall 

```
 sudo ufw status
 sudo ufw allow 5432/tcp
 sudo ufw status
 sudo ufw allow 5432
```

### Installing PGAdmin and bring in same network

```
 sudo docker run --name pgadmin -e "PGADMIN_DEFAULT_EMAIL=name@example.com" -e "PGADMIN_DEFAULT_PASSWORD=admin" -p 5050:80 -d dpage/pgadmin4 
 sudo ufw allow 5050
 sudo docker network create --driver bridge pgnetwork
 docker network connect pgnetwork pgadmin
 sudo docker network connect pgnetwork pgadmin
 sudo docker network connect pgnetwork postgres
 sudo docker network connect pgnetwork some-postgres2
 sudo docker network inspect pgnetwork


```

http://localhost:5050/login  to login and create db and tables

### Set connection in a superset with Postgres

1. Create settings->data connection
2. Create Dataset
3. Create Chart
4. Create Dashboard

![superset_postgres](https://github.com/mnhmilu/poc-superset-pentaho/assets/7475000/de845490-086e-44ab-9ce1-cf8b868414a5)

![pgadmin](https://github.com/mnhmilu/poc-superset-pentaho/assets/7475000/19502b30-b05b-4f8f-8dad-74b1f92ef1e5)


### Reference:

[Superset setup using Docker](https://github.com/developer-advocacy-dremio/quick-guides-from-dremio/blob/main/guides/superset-dremio.md)

[PgAdmin with Docker](https://www.steadylearner.com/blog/how-to-set-up-postgresql-and-pgadmin-with-docker-51h)
