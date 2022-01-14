FROM golang:1.17-alpine AS build
RUN wget https://github.com/jpillora/installer/archive/refs/tags/v0.2.9.tar.gz && \
        mkdir build && \
        tar -xvzf *.tar.gz && \
        cd installer* && \
        CGO_ENABLED=0 go build -o /installer .

FROM alpine:latest AS certs
RUN apk add --no-cache ca-certificates

FROM scratch
COPY --from=certs /etc/ssl /etc/ssl
COPY --from=build /installer /installer
EXPOSE 3000
ENTRYPOINT ["/installer"]
