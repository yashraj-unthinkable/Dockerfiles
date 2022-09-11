FROM node:16.17.0 AS build
COPY code/ /home/node/code
WORKDIR /home/node/code
RUN ["npm", "i"]
RUN ["npm", "run", "build"]

FROM nginx:alpine AS server
COPY --from=build /home/node/code/build /usr/share/nginx/html/
COPY nginx.conf /etc/nginx/conf.d/default.conf
