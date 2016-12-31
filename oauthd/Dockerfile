# Containerized version of [oauthd](https://www.npmjs.org/package/oauthd)

FROM node
MAINTAINER Beerend Lauwers, <beerendlauwers@gmail.com>

# grunt
RUN npm install -g grunt-cli

# oauthd
RUN npm install -g oauthd

# instance will be named "default-oauthd-instance"
RUN /usr/local/bin/oauthd init --default

# set workdir to default instance location.
WORKDIR /default-oauthd-instance

# the front plugin was complaining restify was not installed,
# so we run npm install again here.
RUN cd ./plugins/front && npm install

# add config.js to the default oauthd instance.
ADD config.js ./

EXPOSE 6284
ENTRYPOINT ["/usr/local/bin/oauthd", "start"] 
