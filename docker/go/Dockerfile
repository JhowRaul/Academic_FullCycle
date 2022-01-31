FROM golang:alpine AS builder

RUN apk update && apk add --no-cache git

WORKDIR /go/src/app
COPY . .

RUN go get -d -v
RUN go build -o /go/bin/hello

FROM scratch
COPY --from=builder /go/bin/hello /go/bin/hello

CMD ["/go/bin/hello"]
