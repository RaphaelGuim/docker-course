FROM node:14

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

VOLUME [ "app/feedback" ]

EXPOSE 3000

CMD ["node", "app.mjs"]