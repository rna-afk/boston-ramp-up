FROM golang AS GOAPP
WORKDIR /go/src/github.com/anarayan/goapp
COPY main.go main.go
RUN CGO_ENABLED=0 GOOS=linux go build -a -installsuffix cgo -o app .

FROM ubi8
WORKDIR /root/
COPY --from=GOAPP /go/src/github.com/anarayan/goapp/app .
ENTRYPOINT ["./app"]
