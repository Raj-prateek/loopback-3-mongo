FROM node:14-alpine3.12

USER www-data
RUN mkdir -p /home/node/app

WORKDIR /home/node/app

COPY --chown=node package*.json ./

RUN npm install
COPY --chown=www-data . .
RUN npm run build
ENV HOST=0.0.0.0 PORT=3000

EXPOSE ${PORT}
CMD [ "npm", "run", "start" ]