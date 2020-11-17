FROM node:8.16.1
ENV API_HOST=api:9090
ENV PORT=7777

WORKDIR /home/node

ARG NODE_ENV
ENV NODE_ENV $NODE_ENV

COPY package.json /home/node
RUN npm install
COPY . /home/node
USER node
EXPOSE 7777
CMD [ "npm", "start" ]
