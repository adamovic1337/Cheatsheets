# Docker Cheatsheet
For whole list of commands and options check the [documentation](https://docs.docker.com/engine/reference/run/).

## Manage Images
### List images
```powershell
docker images [options] [repository]
```
- `--all, -a`: Show all images (default hides intermediate images)

### Download an image from a Docker Hub
```powershell
docker pull [options] <image name>[:tag]
```
- `--all-tags, -a`: Download all tagged images in the repository
- `--platform`: Set platform if server is multi-platform capable

### Build an image from a Dockerfile
```powershell
docker build [options] <path|url>
```
- `--tag, -t`: Name and optionally a tag in the `name:tag` format
- `--file, -f`: Name of the Dockerfile (Default is PATH/Dockerfile)

### Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE
```powershell
docker tag <image id|image name> <docker id>/<project name>:<version>
```

### Create a new image from a container’s changes
```powershell
docker commit [options] <container id>
```
- `--change, -c`: Apply Dockerfile instruction to the created image
- `--author, -a`: Author 
- `--message, -m`: Commit message

### Remove unused data
```powershell
docker system prune
```
- `--all, -a`: Remove all unused images not just dangling ones
- `--force, -f`: Do not prompt for confirmation

### Remove one or more images
```powershell
docker image rm
```
- `--force, -f`: Force removal of the image

### Remove unused images
```powershell
docker image prune [options]
```
- `--all, -a`: Remove all unused images, not just dangling ones
- `--force, -f`: Force removal of the image

## Manage Container
### Create a new container
```powershell
docker create [options] <image name>
```
- `--name`: Assign a name to the container

### Start one or more stopped containers
```powershell
docker start [options] <image name> [command]
```
- `--attach, -a`: Attach STDOUT/STDERR and forward signals
- `--interactive, -i`: Attach container’s STDIN

### Create and run a new container from an image
```powershell
docker run [options] <image name> [command] [arg]
```
- `--add-host`: Add a custom host-to-IP mapping (host:ip)
- `--attach, -a`: Attach to STDIN, STDOUT or STDERR
- `--detach, -d`: Run container in background and print container ID
- `--env, -e`: Set environment variables
- `--hostname, -h`: Container host name
- `--interactive, -i`: Keep STDIN open even if not attached
- `--name`: Assign a name to the container
- `--tty, -t`: Allocate a pseudo-TTY
- `--publish, -p`: Publish a container’s port(s) to the host
- `--volume, -v`: Bind mount a volume

### Execute a command in a running container
```powershell
docker exec [options] <container id> <command>
```
 - `--detach, -d`: Detached mode: run command in the background
 - `--env, -e`: Set environment variables
 - `--env-file`: Read in a file of environment variables
 - `--interactive, -i`: Keep STDIN open even if not attached
 - `--tty, -t`: Allocate a pseudo-TTY
 - `--env-file`: Read in a file of environment variables
 - `--user, -u`: Username or UID
 - `--workdir, -w`: Working directory inside the container

### List running containers
```powershell
docker ps [options]
```
 - `--all, -a`: Show all containers (default shows just running)
 - `--quiet, -q`: Only display container IDs
 - `--size, -s`: Display total file sizes

### Stop one or more running containers
```powershell
docker stop <container id> 
```

### Kill one or more running containers
```powershell
docker kill <container id> 
```

### Remove one or more containers
```powershell
docker rm <container id> 
```

## Info & Stats
### Fetch the logs of a container
```powershell
docker logs [options] <container id> 
```
- `--details`: Show extra details provided to logs
- `--follow, -f`: Follow log output
- `--since`: Show logs since timestamp
- `--tail, -n`: Number of lines to show from the end of the logs
- `--timestamps, -t`: Show timestamps
- `--until`: Show logs before a timestamp

### Show the Docker version information
```powershell
docker version
```

### Show docker disk usage
```powershell
docker system df
```

## Docker Compose
### Create and start containers
```powershell
docker compose up [options] [service...]
```
- `--detach, -d`: Detached mode: Run containers in the background
- `--build`: Build images before starting containers

### List containers
```powershell
 docker compose ps [options]
```
- `--all, -a`: Show all stopped containers 
- `--status`: Filter services by status. Values: [paused | restarting | removing | running | dead | created | exited]
- `--services`: Display services 

### Stop and remove containers, networks
```powershell
docker compose down [options]
```
- `--remove-orphans`: Remove containers for services not defined in the Compose file
- `--rmi`: Remove images used by services. “local” remove only images that don’t have a custom tag (“local”|”all”)
- `--timeout, -t`: Specify a shutdown timeout in seconds
- `--volumes, -v`: Remove named volumes declared in the `volumes` section of the Compose file and anonymous volumes attached to containers

### Starts existing containers for a service
```powershell
docker compose start
```

### Stop services
```powershell
docker compose stop
```