---
title: Docker Commands
category: Docker
order: 1
---

## Find All Containers
``` bash
docker ps -a
```

## Find Running Containers
``` bash
docker ps 
```

## Start Up Failed Container and Attach to STDIO / STDERR
``` bash
docker start --attach 8b
```

## List All Docker Images
``` bash
docker images -a
```

## Kill All Containers
``` bash
docker kill `docker ps -aq`
```

## Remove All Images
``` bash
docker rmi `docker images -aq`
```

> We can use the partial unique image id (4f) or a longer version copied from output like (4f803ffceb53) or the long name like (4f803ffceb5301bd94cfa2b9f931a36493effd50e9d14a53586ffb27a48bb580)

## Building .NET Core App and Uploading to ACR
``` bash
dotnet publish -c Release out
cp Dockerfile out
docker build -t my-tag:v1 out
docker run -d -p 8080:8080 my-tag:v1
docker login myregistry.azurecr.io -u guid -p P4SSW0rd!
docker tag 4f myregistry.azurecr.io/samples/my-tag
docker push myregistry.azurecr.io/samples/my-tag
```

## Get an Interactive Terminal Inside Running Container
``` bash
docker exec -it 4f bash
```
