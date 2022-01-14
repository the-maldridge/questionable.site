FROM golang:1.16-alpine AS build
WORKDIR /links
RUN apk add --no-cache git build-base && \
        git clone http://git.fsh.ee/i/link.git/ . && \
        go build -o /tmp/links .

FROM alpine:latest
COPY --from=build /tmp/links /links
COPY --from=build /links/index.html /
RUN apk add --no-cache sqlite
ENTRYPOINT ["/links"]
EXPOSE 8080
