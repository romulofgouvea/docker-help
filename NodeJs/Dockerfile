FROM node:10-alpine

WORKDIR /usr/app
COPY yarn*.json ./

RUN yarn

COPY . .

EXPOSE 3000
CMD [ "yarn","start" ]