FROM docker
RUN apk update
RUN apk add git
RUN apk add bash
WORKDIR /app
COPY ./builder.sh .
RUN chmod +x ./builder.sh
ENTRYPOINT ["/bin/bash", "/app/builder.sh"]
