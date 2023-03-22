FROM golang:1.16-alpine
EXPOSE 8080
WORKDIR /usr/src/app
COPY . .
#ENV REQUEST_ORIGIN=http://localhost
RUN adduser -S appuser && go build && chown appuser .
USER appuser
CMD ["./server"]
