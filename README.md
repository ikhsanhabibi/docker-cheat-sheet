# docker-cheat-sheet
docker cheat sheet


- Hands-on with Docker- A step by step tutorial to getting started with Docker on any machine: https://pallawi-ds.medium.com/hands-on-with-docker-a-step-by-step-tutorial-to-getting-started-with-docker-on-any-machine-55ec923a2b02


# check images
```
docker images
```

# pull docker images
```
docker pull [image name]
docker pull ubuntu
```

# remove docker image
```
docker rmi [image name]
```

# delete all the images
```
docker rmi -f $(docker images -aq)
```

# rename docker images
```
docker tag image-ID [new-name]
```

# remove tag in docker images
```
docker rmi REPOSITORY:TAG
```

# list all existing container
```
docker ps -a
```

# list running container
```
docker ps
```

# run docker image
```
docker run -t -d --name [image tag] [image name]
docker run -t -d --name latest ubuntu
```

# start container
```
docker start <CONTAINER_ID> or <CONTAINER_NAMES>
docker start 5c2f4b9516c7
or 
docker start containername
```

# stop container
```
docker stop [container ID]
docker stop 67a5052f3154
```

# remove container
```
docker rm [container ID]
```

# delete all containers including its volumes use
```
docker rm -vf $(docker ps -aq)
```

# Build an image from the Dockerfile
```
docker build -t [docker image] .
```

# update docke images
```
 docker build -t REPO:TAG .
```
------------------------------------------------------
### How to Run PostgreSQL and pgAdmin Using Docker

# create docker-compose.yml file in the directory
- db port meaning: the ports tag is used to define both host and container ports. It maps port 5432 on the host to port 5432 on the container.
```
version: '3.8'
services:
  db:
    container_name: postgres_container
    image: postgres
    restart: always
    environment:
      POSTGRES_USER: postgres
      POSTGRES_PASSWORD: root
      POSTGRES_DB: test_db
    ports:
      - "5432:5432"
  pgadmin:
    container_name: pgadmin4_container
    image: dpage/pgadmin4
    restart: always
    environment:
      PGADMIN_DEFAULT_EMAIL: admin@admin.com
      PGADMIN_DEFAULT_PASSWORD: root
    ports:
      - "5050:80"
  adminer:
    container_name: adminer_container
    image: adminer
    restart: always
    ports:
      - 8080:8080
```

# starts and runs the entire app
```
docker compose up -d
```

# grab the PostgreSQL container id
```
docker ps -a
```
![image](https://user-images.githubusercontent.com/33756873/168673182-02505214-c51c-4a3a-a243-82116a689552.png)

# extract IPAddress on the running container
```
docker inspect fcc97e066cc8 | grep IPAddress
```
![image](https://user-images.githubusercontent.com/33756873/168674237-dbe014a3-e191-4483-b449-73562f4dfd53.png)


# open PgAdmin
- access the pgadmin4 via your favorite web browser by vising the URL http://localhost:5050/. Use the admin@admin.com for the email address and root as the password to log in.

![image](https://user-images.githubusercontent.com/33756873/168674105-ce995386-9170-42b9-882f-2ddaf0083906.png)


- Click Servers > Create > Server to create a new server.
![image](https://user-images.githubusercontent.com/33756873/168674144-c70e559b-ec7f-4d8d-b27d-cddac3ff0c5f.png)

- better write the host with the container name
![image](https://user-images.githubusercontent.com/33756873/168674708-e363cc6b-6130-4734-b86b-959857f52543.png)


