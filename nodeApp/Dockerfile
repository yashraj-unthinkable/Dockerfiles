FROM alpine:latest

RUN apk add --update nodejs npm

RUN addgroup -S node && adduser -S node -G node

USER node

WORKDIR /home/node

COPY --chown=node:node code/package-lock.json code/package.json ./

RUN npm i

COPY --chown=node:node code/ .

CMD ["node", "index.js"]

EXPOSE 3000
