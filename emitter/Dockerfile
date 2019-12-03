FROM node:10

# set working directory
WORKDIR /root/emitter

# copy project file
COPY package*.json ./

# set NODE_ENV
ENV NODE_ENV production

# install node packages
RUN npm install

# copy app files
COPY . .

# Set tini as entrypoint
ENTRYPOINT ["/sbin/tini", "--"]

#application server
EXPOSE 8080

CMD [ "node", "index.js" ]