FROM golang:alpine as builder


WORKDIR /go/src/app
COPY . .

RUN go get -d -v ./...
RUN go install -v ./...


FROM scratch

COPY --from=builder /go/bin/app /go/bin/app

CMD ["/go/bin/app"]

