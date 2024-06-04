This is bunch of dockerfile for my ansible labs 

# How to use
## Change Directory
```bash
cd ubuntu
```
## Building  Docker Containers
```bash
docker build -t ubuntu_ssh -f Dockerfile .
```

## Run Docker Containers:
```bash
docker run -d -P --name target_ubuntu ubuntu_ssh
```
# Verify 
## Get ip address of docker container
```bash
 docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' target_ubuntu
```
## SSH 
```
ssh root@172.17.0.2
```




