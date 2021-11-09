# use alpine linux with node and yarn and the user "node"
FROM node:17.0.1-alpine3.14

LABEL Description="All the node modules on a shared volume. If the package.json is changed. Rebuild the image."

# ENV NPM_CONFIG_LOGLEVEL warn

USER root

# set the working directory to the user home
WORKDIR /home/node

# copy files for yarn
COPY ./package.json /home/node/package.json
COPY ./yarn.lock /home/node/yarn.lock
COPY ./.yarnrc /home/node/.yarnrc

# install from package.json set and remove a cache folder to reduce the image size
RUN set -ex; yarn install --pure-lockfile --production=false --cache-folder ./tmp/.ycache; rm -rf ./tmp/.ycache;





