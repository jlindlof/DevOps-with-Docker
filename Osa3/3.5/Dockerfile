FROM ubuntu:16.04 as build-stage

WORKDIR /app
RUN apt-get update && apt install curl wget git gcc g++ make -y
RUN git clone https://github.com/docker-hy/frontend-example-docker.git
RUN mv ./frontend-example-docker/* ./
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash
RUN apt-get install -y nodejs
RUN npm install
RUN npm run build

FROM node:alpine

ENV NPM_CONFIG_PREFIX=/home/node/.npm-global
ENV PATH=$PATH:/home/node/.npm-global/bin
ENV API_URL=http://localhost:8000
COPY --from=build-stage /app/dist /app/dist
RUN npm install -g serve
USER app
CMD ["serve", "-s", "-l", "5000", "/mydir/dist"]
