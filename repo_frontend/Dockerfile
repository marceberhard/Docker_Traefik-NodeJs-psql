FROM node:8.16.1

ARG PORT
ARG API_HOST

ENV API_HOST $API_HOST
ENV PORT $PORT

RUN addgroup --system *** && adduser --ingroup *** --system --shell /bin/false ***
RUN mkdir -p /home/***/ && chown -R cldinf:cldinf /home/***/

COPY . /home/***/
COPY package.json /home/***
RUN  chown -R ***:*** /home/***/

WORKDIR /home/***/
RUN npm install
RUN npm audit fix
USER ***

EXPOSE 7777
CMD [ "npm", "start" ]
