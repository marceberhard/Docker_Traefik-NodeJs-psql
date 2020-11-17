FROM node:8.16.1

WORKDIR /home/node
ENV PORT=9090
ENV DB=postgres://postg8:postg8@postgres/dbdocker

ARG NODE_ENV
ENV NODE_ENV $NODE_ENV

COPY package.json /home/node
RUN npm install

COPY . /home/node

# replace this with your application's default port
EXPOSE 9090
CMD [ "npm", "start" ]
