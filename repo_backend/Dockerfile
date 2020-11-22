FROM node:8.16.1

ARG PORT
ARG DB

ENV PORT $PORT
ENV DB $DB

RUN addgroup --system cldinf && adduser --ingroup cldinf --system --shell /bin/false cldinf
RUN mkdir -p /home/cldinf/ && chown -R cldinf:cldinf /home/cldinf/


COPY . /home/cldinf/
COPY package.json /home/cldinf
RUN  chown -R cldinf:cldinf /home/cldinf/

WORKDIR /home/cldinf/
RUN npm install
RUN npm audit fix

USER cldinf

EXPOSE 9090
CMD [ "npm", "start" ]
