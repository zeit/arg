FROM mhart/alpine-node:11.3.0
ARG CODECOV_TOKEN
ENV $CODECOV_TOKEN=${CODECOV_TOKEN}
WORKDIR /src
COPY package.json ./
RUN npm i
COPY index.js test.js .git ./
RUN npm run test
# install git & codecov
RUN apk update && apk upgrade && \
    apk add --no-cache bash git openssh &&\
    npm install -g codecov &&\
    codecov

