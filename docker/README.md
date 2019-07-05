# Docker commands

## STATUS
```
docker --version
docker images ls -a
docker container ls -all
docker ps -a
```

* grep docker log
```
docker logs testapp 2>&1 | grep "fail"
```

## PULL
```
docker pull hello-world
```

## BUILD 
* build
```
docker build -t testapp:trunk -f webapp\testapp\docker\Dockerfile_cmd webapp\testapp\docker
```

## AWS integration
* tag and push to AWS
```
aws ecr get-login --region eu-west-1
aws ecr get-authorization-token --region eu-west-1 --output text --query authorizationData[].authorizationToken | base64 -d | cut -d: -f2
docker login -u AWS -p xYz... -e none https://123456.dkr.ecr.us-east-1.amazonaws.com
docker tag testapp:trunk 123456.dkr.ecr.eu-west-1.amazonaws.com/testapp/testapp:trunk
docker push 123456.dkr.ecr.eu-west-1.amazonaws.com/testapp/testapp
```

## RUN
```
docker run hello-world
docker run -p 81:80 nginx
docker run --detach --publish 81:80 --name webserver nginx
docker run -d -i -p 8080:8080 -v /home/ec2-user/uilog:/opt/tomcat/logs -e DEPLOY_SCENARIO=DEV_SENTRUM testapp
```

* Exec bash
```
docker exec -it 7b7501f3f8a1 /bin/bash
```

## CLEAN
* remove all unused objects
```
docker system prune
```
* clean unused images
```
docker images prune
```
* stop container
```
docker container stop CONTAINER_ID / CONTAINER_NAME
```
* remove container
```
docker container rm CONTAINER_ID / CONTAINER_NAME
```
* stop and remove (force) running containers
```
docker container -f rm $(docker container ls -aq)
```