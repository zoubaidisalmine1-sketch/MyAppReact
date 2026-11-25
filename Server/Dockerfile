FROM node:lts-alpine

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .
FROM node:lts-alpine
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 9000
CMD ["npm", "start"]
EXPOSE 9000

CMD ["npm", "start"]