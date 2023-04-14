### 2. Run 
Run a container from the myimage version 1.0
image, name the running container
“web” and expose port 80 externally,
mapped to port 5000 inside the container.
```
docker run -p 80:5000 --name webapp_1 myimage:1.0
```
or
```
docker run -d --rm -p 80:5000 --name webapp_1 myimage:1.0
```
Now, open your browser, type "localhost" and hit enter

Stop a running container through SIGTERM
```
docker stop webapp_1
```

Stop a running container through SIGKILL
```
docker kill webapp_1
```

Ref: https://en.wikipedia.org/wiki/Signal_(IPC) for SIGTERM vs SIGKILL

List the running containers (add -a to include stopped containers)
```
docker ps
```

Delete all running and stopped containers
```
docker container rm -f $(docker ps -aq)
```

Print the last 100 lines of a container’s logs
```
docker logs --tail 100 webapp_1
```

### 3. Share
Pull an image from a registry
```
docker pull myimage:1.0
```

Retag a local image with a new image name
and tag
```
docker tag myimage:1.0 myrepo/myimage:2.0
```

Push an image to a registry
```
docker push myrepo/myimage:2.0
```

### Docker CLI cheatsheet
![Alt text](images/dockercheatsheet8.png?raw=true)
