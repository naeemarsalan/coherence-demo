FROM golang:1.20 as build
WORKDIR /build
COPY . .
RUN CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build -o ./go-demo .

FROM scratch
WORKDIR /files/
COPY --from=build go-demo .
ENTRYPOINT ["/files/go-demo"]
CMD []
