FROM node

# The default WORKDIR is the root . All the instructions bellow will be executed inside WORKDIR
WORKDIR /app 

COPY package.json /app

RUN npm install

COPY . /app

EXPOSE 80

CMD [ "node", "server.js" ]
