FROM golang:1.16
EXPOSE 8080
WORKDIR /usr/src/app
COPY . .
RUN go build
RUN test ./...
#Enable the env variable if running the full project with reverse-proxy
#ENV REQUEST_ORIGIN=http://localhost
RUN adduser appuser
USER appuser
CMD ["./server"]
