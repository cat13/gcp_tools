# usage

## Build docker image
```docker build -t gcp-db-proxy .```

## create an environment target

### create a folder which retain k8s and gcp config files.
```mkdir -p ~/gcp-db-proxy/staging/config
   mkdir -p ~/gcp-db-proxy/staging/kube
   ...

### initialize the config file of container. otherwise the docker compose will exist with error
docker run -it --mount type=bind,source=/home/scao/dockerenv/vivi/prod/config,target=/root/.config,bind-propagation=shared --mount type=bind,source=/home/scao/dockeren
v/vivi/prod/kube,target=/root/.kube,bind-propagation=shared vivi-db-proxy

### create a docker compose file with reference the folder above
 see example in staging.

 
### run docker compose
```docker-compose up -d```

### connect db with the host port defined in docker compose file
