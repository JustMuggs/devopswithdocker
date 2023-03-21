FROM ubuntu
EXPOSE 5000
WORKDIR /usr/src/app
RUN apt-get update
RUN apt-get install -y curl
RUN curl -sL https://deb.nodesource.com/setup_16.x | bash
RUN apt-get install -y nodejs
COPY . .
RUN npm install
#Enable the env variable if running the full project with reverse-proxy
#ENV REACT_APP_BACKEND_URL=http://localhost/api
RUN npm run build
RUN npm install -g serve
RUN useradd -m appuser
RUN chown appuser .
USER appuser
CMD ["serve", "-s", "-l", "5000", "build"]
