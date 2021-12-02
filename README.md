# Overview

Some quickstart helpers because I always forget the correct way to spin up the DBs locally.

# MySQL

## Start MySQL

**username:** `root`
**password:** `password`

Run mysql:
```
docker run -p 3306:3306 -e MYSQL_ROOT_PASSWORD=password -e -d mysql:latest
```

## Verify connectivity

```
mysql --user=root --host=127.0.0.1 --port=3306 --password
```

## Helper commands

- Show DB
- Show tables

# Postgres


```
docker run -p 5432:5432 -e POSTGRES_USER=postgres -e POSTGRES_PASSWORD=password -d postgres:latest
```

## Verify connectivity

```
# Admin
psql --username=postgres --host=127.0.0.1 --port=5432 --password

# DB-specific user
psql --username=odosuser --host=127.0.0.1 --port=5432 --dbname=odos --password
```

## Making a DB

- Show DBs: `\l`
- Use DB: `\c odos`
- Show tables: `\dt`
- Make DB (see below)


```
CREATE DATABASE odos;
CREATE USER odosuser WITH PASSWORD 'odospassword';
GRANT ALL PRIVILEGES ON DATABASE odos TO odosuser;
```
