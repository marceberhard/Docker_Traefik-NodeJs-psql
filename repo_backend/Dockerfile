FROM node:8.16.1

ARG PORT
ARG DB

ENV PORT $PORT
ENV DB $DB

RUN addgroup --system *** && adduser --ingroup *** --system --shell /bin/false ***
RUN mkdir -p /home/***/ && chown -R ***:*** /home/***/


COPY . /home/***/
COPY package.json /home/***
RUN  chown -R ***:*** /home/***/

WORKDIR /home/***/
RUN npm install
RUN npm audit fix

USER ***

EXPOSE 9090
CMD [ "npm", "start" ]
