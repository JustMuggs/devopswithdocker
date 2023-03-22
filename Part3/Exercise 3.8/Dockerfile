FROM node:16-alpine as builder
WORKDIR /usr/src/app
COPY . .
#ENV REACT_APP_BACKEND_URL=http://localhost/api
RUN npm install && \
    npm run build

FROM node:16-alpine
EXPOSE 5000
WORKDIR /usr/src/app
RUN npm install -g serve && \
    adduser -S appuser && \
    chown appuser .
USER appuser
COPY --from=builder /usr/src/app/build /usr/src/app/build
CMD ["serve", "-s", "-l", "5000", "build"]
