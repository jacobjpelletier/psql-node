# udacity full stack javascript 
## psql-node
The scope of this repo is to 1. start a postgres docker container, and 2. perform basic psql DB operations
### commands:
#### helpful guide: https://github.com/benawad/graphql-typescript-stripe-example/blob/multi-stage-docker/server/commands.txt
1. create docker container at postgres port 5432. ports: localhost:postgres
2. postgres will know e variables
3. -v flag sets where to set data 
4. get container id (#####) from `container ls`
5. -it for interactive console
```
docker run -p 5432:5432 -d 
    -e POSTGRES_PASSWORD=postgres 
    -e POSTGRES_USER=postgres 
    -e POSTGRES_DB=udacity-node-example 
    -v pgdata:/var/lib/postgresql/data
    postgres
    
docker exec -it ##### psql -U postgres udacity-node-example
```
6. create a table like this
```
\l List databases
\c Connect to a database
\dt Display Tables in a database
\q Quit out of psql to normal terminal

CREATE TABLE first_things (
id SERIAL PRIMARY KEY,
name VARCHAR(50),
count integer
);
```
7. create plant table
```
CREATE TABLE plants (id SERIAL PRIMARY KEY, name VARCHAR(100), description text, individuals integer, sighting_date date);
INSERT INTO plants (name, description, individuals, sighting_date) VALUES ('Dandelion', 'Fuzzy yellow flowers', 4, '2021-01-01');
```
8. observe the table with `SELECT * FROM plants;`
9. update with`UPDATE plants SET individuals=8 WHERE id=1`;
10. Delete with `DELETE FROM plants WHERE id=1;`