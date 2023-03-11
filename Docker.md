# Docker Cheatsheet
For whole list of commands check [documentation](https://docs.docker.com/engine/reference/run/).

## Manage Images
### List images
```powershell
docker images
```

### Download an image from a Docker Hub
```powershell
docker pull <image name>:<tag>
```
- `--all-tags , -a`: Download all tagged images in the repository
- `--platform`: Set platform if server is multi-platform capable

### Build an image from a Dockerfile
```powershell
docker build <directory>
```

### Remove unused data
```powershell
docker system prune
```
- `--all , -a`: Remove all unused images not just dangling ones
- `--force , -f`: Do not prompt for confirmation

## Manage Container
### Create a new container
```powershell
docker create <image name>
```
- `--name`: Assign a name to the container

### Start one or more stopped containers
```powershell
docker start <image name>
```
- `--attach , -a`: Attach STDOUT/STDERR and forward signals
- `--interactive , -i`: Attach container’s STDIN

### Create and run a new container from an image
```powershell
docker run <image name>
```
- `--detach , -d`: Run container in background and print container ID
- `--env , -e`: Set environment variables
- `--name`: Assign a name to the container
- `--publish , -p`: Publish a container’s port(s) to the host
- `--add-host`: Add a custom host-to-IP mapping (host:ip)
- `--hostname , -h`: Container host name

### Execute a command in a running container
```powershell
docker exec <container id> <command>
```
 - `--detach , -d`: Detached mode: run command in the background
 - `--env , -e`: Set environment variables
 - `--env-file`: Read in a file of environment variables
 - `--interactive , -i`: Keep STDIN open even if not attached
 - `--tty , -t`: Allocate a pseudo-TTY
 - `--env-file`: Read in a file of environment variables
 - `--user , -u`: Username or UID
 - `--workdir , -w`: Working directory inside the container

### List running containers
```powershell
docker ps 
```
 - `--all, -a`: Show all containers (default shows just running)
 - `--quiet , -q`: Only display container IDs
 - `--size , -s`: Display total file sizes

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
docker logs <container id> 
```
- `--details`: Show extra details provided to logs
- `--follow , -f`: Follow log output
- `--since`: Show logs since timestamp
- `--tail, -n`: Number of lines to show from the end of the logs
- `--timestamps. -t`: Show timestamps
- `--until`: Show logs before a timestamp

### Show the Docker version information
```powershell
docker version
```


### Show docker disk usage
```powershell
docker system df
```