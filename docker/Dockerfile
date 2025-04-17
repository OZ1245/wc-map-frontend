# syntax = docker/dockerfile:1

ARG NODE_VERSION=22.14.0

FROM node:${NODE_VERSION}-slim as base

ENV NODE_ENV=development

WORKDIR /app

# Build
FROM base as build

COPY package.json .
COPY package-lock.json .

RUN npm install

# Run
FROM base

COPY . .

CMD [ "npm", "run", "dev" ]