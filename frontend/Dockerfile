
# syntax=docker/dockerfile:1

FROM node:lts-alpine AS build

WORKDIR  /jp

COPY package*.json /jp/

RUN npm i

COPY . .

RUN npm run build

FROM nginx:1.21.6-alpine

COPY --from=build /jp/build /usr/share/nginx/html



