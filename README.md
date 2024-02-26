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




### Reference:

[Superset setup using Docker](https://github.com/developer-advocacy-dremio/quick-guides-from-dremio/blob/main/guides/superset-dremio.md)
