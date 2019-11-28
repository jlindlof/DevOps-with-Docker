
FROM node:10-alpine

RUN apk add --no-cache git && \
    git clone https://github.com/docker-hy/backend-example-docker.git /back && \
    cd /back && \
    npm install && \
    apk del git && \
    adduser -D app  && \
    chown -R app .

USER app
WORKDIR /app
EXPOSE 5000
CMD ["npm", "start"]
