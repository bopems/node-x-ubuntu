# node-x-ubuntu
Start service in container Node with this image Docker
Where 'x' is version of Node.

# Docker Hub
https://cloud.docker.com/u/bopems/repository/docker/bopems/node

# Download Image Docker
```shell
docker pull bopems/node:6-ubuntu
```
or
```shell
docker pull bopems/node:8-ubuntu
```

# Examples Angular App

```yml
FROM bopems/node:6-ubuntu

RUN mkdir -p /app

WORKDIR /app

COPY package*.json /app/

# Repository file (example Nexus), if not exists remove this
COPY .npmrc /root/.npmrc

RUN npm install -g @angular/cli
RUN npm install --production

COPY . /app/

EXPOSE 4200

CMD ["npm", "start"]
```
