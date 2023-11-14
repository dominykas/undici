FROM node:21-alpine@sha256:df76a9449df49785f89d517764012e3396b063ba3e746e8d88f36e9f332b1864

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
