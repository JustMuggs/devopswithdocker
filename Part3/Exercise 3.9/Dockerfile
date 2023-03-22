FROM golang:alpine AS builder
RUN apk update && apk add --no-cache git
WORKDIR /app
COPY . .
#ENV REQUEST_ORIGIN=http://localhost
RUN go get -d -v && go build && adduser -S appuser && chown appuser .

FROM scratch
EXPOSE 8080
WORKDIR /app
COPY --from=builder /app/server /app/server
COPY --from=builder /etc/passwd /etc/passwd
USER appuser
CMD ["./server"]
