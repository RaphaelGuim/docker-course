FROM node

# The default WORKDIR is the root . All the instructions bellow will be executed inside WORKDIR
WORKDIR /app 

COPY . /app

RUN npm install

EXPOSE 80

CMD [ "node", "server.js" ]
