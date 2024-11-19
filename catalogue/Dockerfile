FROM node:hydrogen-alpine3.20
EXPOSE 8080
WORKDIR /opt/server
COPY package.json .
COPY server.js .
RUN npm install
ENV MONGO=true
CMD ["node", "server.js"]
