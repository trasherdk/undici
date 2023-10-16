FROM node:20-alpine@sha256:37750e51d61bef92165b2e29a77da4277ba0777258446b7a9c99511f119db096

ARG UID=1000
ARG GID=1000

RUN apk add -U clang lld wasi-sdk
RUN mkdir /home/node/undici

WORKDIR /home/node/undici

COPY package.json .
COPY build build
COPY deps deps
COPY lib lib

RUN npm i

USER node
