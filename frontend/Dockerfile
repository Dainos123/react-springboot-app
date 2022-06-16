
# syntax=docker/dockerfile:1

FROM node:lts-alpine AS builder

WORKDIR  /jp

COPY package*.json /app/

RUN npm i

COPY . .

RUN npm run build

FROM nginx:1.21.6-alpine

COPY --from=builder /jp/build /usr/share/nginx/html



