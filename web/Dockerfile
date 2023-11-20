FROM node:16-alpine

WORKDIR /app/web

COPY package*.json /app/web/

RUN npm i -g pnpm && pnpm install && apk add xdg-utils

COPY . /app/web/

EXPOSE 3000

CMD ["pnpm", "dev"]