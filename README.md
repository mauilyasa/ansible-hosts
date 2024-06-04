This is bunch of dockerfile for my ansible labs 

## How to use
```bash
# Change Directory
cd ubuntu

# Building and Running Docker Containers
docker build -t ubuntu_ssh -f Dockerfile .

# Run Docker Containers:
docker run -d -P --name ansible_target_ubuntu ubuntu_ssh
```

