FROM node:12.10.0-alpine
RUN npm install --save-dev prettier@>=1.13.0 
WORKDIR /usr/app

COPY package*.json ./
RUN npm ci -qy

COPY . .

EXPOSE 5000

RUN npm audit fix --force
RUN npm build

CMD ["npm", "start"]
