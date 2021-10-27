FROM node:16-alpine

# Create app directory
WORKDIR /usr/src/railway

# Install yarn

RUN npm install --global yarn

COPY server/package.json .
COPY server/yarn.lock .

RUN yarn install --production && \
    yarn run build --prod

# Bundle app source
COPY server/* .

EXPOSE 3000
CMD [ "node", "server.js" ]