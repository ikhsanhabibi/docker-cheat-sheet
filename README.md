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

# list container
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
