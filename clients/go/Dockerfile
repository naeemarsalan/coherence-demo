FROM golang:1.18.10 as build
COPY . .
RUN CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build -o ./go-demo main.go

FROM scratch
WORKDIR /files/
COPY --from=build go-demo .
ENTRYPOINT ["/files/go-demo"]
CMD []
