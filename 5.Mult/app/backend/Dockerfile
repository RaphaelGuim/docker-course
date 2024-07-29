FROM node

WORKDIR /app

COPY package.json .

RUN npm install

COPY . . 

EXPOSE 80

CMD ["node", "app.js"]




#MONGO
# docker run --name mongodb --rm -d -p 27017:27017 mongo

#Build
#docker build -t goals-node .


#RUN
#docker run --rm -d -p 80:80 --name goals-backend goals-node