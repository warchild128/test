FROM alpine:3.10.3

# install node
RUN apk add --no-cache nodejs tini

# set working directory
WORKDIR /root/emitter

# copy project file
COPY package.json .

# set NODE_ENV
ENV NODE_ENV production

# install node packages
RUN npm install && \
    npm cache clean && \
    apk del .build-dep && \
    rm -rf /tmp/*

# copy app files
COPY ./emitter .

# Set tini as entrypoint
ENTRYPOINT ["/sbin/tini", "--"]

#application server
EXPOSE 5000

CMD npm run start