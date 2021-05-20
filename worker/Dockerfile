# PRODUCTION ENVIRONMENT DOCKERFILE
FROM node:14.14.0-alpine

USER node

RUN mkdir -p /home/node/app

WORKDIR '/home/node/app'

COPY --chown=node:node ./package.json ./

RUN npm install

#COPY ./package.json ./

COPY --chown=node:node ./ ./

#COPY ./ ./

CMD ["npm", "run", "start"]
# we are using 'start' here because we have mentioned a script as "start": "node index.js" in package.json of current directory
