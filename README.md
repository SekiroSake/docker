# docker
A note about docker

## Docker container
- Foreground(default) vs detached(-d option)


You can start a docker container in detached mode with a -d option. So the container starts up and run in background. That means, you start up the container and could use the console after startup for other commands.

The opposite of detached mode is foreground mode. That is the default mode, when -d option is not used. In this mode, the console you are using to execute docker run will be attached to standard input, output and error. That means your console is attached to the containers process.

In detached mode, you can follow the standard output of your docker container with docker logs -f <container_instance_name>.

I always use the detached mode to run my containers. I hope i could explain it a little bit clearer.
```
docker run -d busybox:1.24 sleep 1000
```
- Find all running docker container
```
docker ps
```
- Find all docker container (including stop one)
```
docker ps -a
```
- stop
```
docker run --rm busybox:1.24 sleep 1
```

- name a container
```
docker run --name hello_world busybox:1.24
```

- docker inspect: displays low level information about a container or image

```
docker inspect 6518322bbf494022f297ea40f36f5d25a79b2729b245b4405c1ff65655dd786d
```

## Docker port mapping and docker logs
```
docker run -it -p 8888:8080 tomcat:8.0
```

### All changes are writen in the container's writable layer , when the container was deleted, the writeable layer also be deleted, but the image will stay the same.

