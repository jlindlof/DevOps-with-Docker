FROM ubuntu:16.04

RUN apt-get update && apt-get install -y curl && \
    curl -sL https://deb.nodesource.com/setup_10.x | bash && \
    apt-get install -y git nodejs && \
    git clone https://github.com/docker-hy/backend-example-docker.git /app && \
    cd /app && npm install && \
    apt-get purge -y --auto-remove curl git && \
    useradd app && \
    chown -R app /app

WORKDIR /app
USER app
EXPOSE 8000
CMD ["npm", "start"]
