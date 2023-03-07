FROM golang:alpine3.17 as builder

WORKDIR /root

RUN go mod init hello

COPY hello.go /root

run go build


FROM scratch as runtime

WORKDIR /root

COPY --from=builder /root/hello /root

CMD ["./hello"]



