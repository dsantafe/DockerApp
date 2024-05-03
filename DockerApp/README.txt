#Docker run
docker run -d --name dockerapp \
-e "ASPNETCORE_ENVIRONMENT=Development" \
-p 8080:80 \
dockerapp:v0.0.1

#Build docker image
$ docker build -t dockerapp:v0.0.1 .
$ docker images

$ az acr login --name <acrName>

#Push image to Azure Container Registry
$ docker tag dockerapp:v0.0.1 <acrName>.azurecr.io/dockerapp:v0.0.1
$ docker push <acrName>.azurecr.io/dockerapp:v0.0.1

$ az login --tenant <tenantId>
$ docker login azure --tenant-id <tenantId>
$ docker context create aci aci-ctx-local
$ docker context ls
$ docker context use aci-ctx-local
$ docker compose up