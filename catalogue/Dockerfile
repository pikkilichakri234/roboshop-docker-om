FROM node:23.2.0-alpine3.20
EXPOSE 8080
RUN addgroup -S cart && adduser -S cart cart
WORKDIR /opt/server
RUN chown -R cart:cart /opt/server
USER cart
COPY package.json .
COPY server.js .
RUN npm install
CMD ["node", "server.js"]
