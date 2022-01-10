# psql-node
## commands:
1. create docker container at postgres port 5432. ports: localhost:postgres
2. postgres will know e variables
3. -v flag sets where to set data 
4. get container id (#####) from `container ls`
5. -it for interactive console
```
docker run -p 5432:5432 -d \
    -e POSTGRES_PASSWORD=postgres \
    -e POSTGRES_USER=postgres \
    -e POSTGRES_DB=udacity-node-example \
    -v pgdata:/var/lib/postgresql/data \
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