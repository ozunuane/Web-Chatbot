FROM node:12.10.0-alpine
WORKDIR /usr/app

COPY package*.json ./
RUN npm ci -qy

COPY . .
EXPOSE 5000
RUN npm install -g npm-install-peers
RUN npm audit fix -i
RUN npm build

CMD ["npm", "start"]
