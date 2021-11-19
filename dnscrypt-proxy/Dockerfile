FROM golang:1.17-alpine AS build
ENV CGO_ENABLED=0
RUN go install -tags netgo -a -installsuffix netgo -ldflags '-extldflags "-static"' github.com/dnscrypt/dnscrypt-proxy/dnscrypt-proxy@2.1.1
FROM alpine
COPY --from=build /go/bin/dnscrypt-proxy /dnscrypt-proxy
RUN apk add --no-cache ca-certificates
ENTRYPOINT [ "/dnscrypt-proxy" ]
