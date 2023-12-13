## Building Images

### Create and use builder
````
docker buildx create --name mybuilder
docker buildx use mybuilder
````

### Build images and run
For example build 8.3-bullseye image
````
cd 8.3-bullseye
docker buildx build . --push --platform linux/arm/v7,linux/amd64,linux/arm64 --tag jcfrane/php:8.3-bullseye
````
