FROM golang:1.17-alpine AS build
ENV CGO_ENABLED=0
RUN go install -tags netgo -a -installsuffix netgo -ldflags '-extldflags "-static"' github.com/dnscrypt/dnscrypt-proxy/dnscrypt-proxy@2.1.1
FROM alpine
COPY --from=build /go/bin/dnscrypt-proxy /dnscrypt-proxy
COPY dnscrypt-proxy.toml /dnscrypt-proxy.toml
RUN addgroup -S dnscrypt && adduser -S dnscrypt -G dnscrypt
RUN apk add --no-cache ca-certificates
USER dnscrypt
EXPOSE 5054/udp
EXPOSE 5054/tcp
ENTRYPOINT [ "/dnscrypt-proxy" ]
