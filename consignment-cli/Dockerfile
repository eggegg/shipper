# FROM golang:1.9.0 as builder

# WORKDIR /go/src/github.com/eggegg/shipper/consignment-cli

# COPY . .

# RUN go get -u github.com/golang/dep/cmd/dep
# RUN dep init && dep ensure
# RUN CGO_ENABLED=0 GOOS=linux go build -a -installsuffix cgo .


FROM alpine:latest

RUN apk --no-cache add ca-certificates

RUN mkdir /app
WORKDIR /app
COPY consignment.json /app/consignment.json
# COPY --from=builder /go/src/github.com/eggegg/shipper/consignment-cli/consignment-cli .
ADD consignment-cli /app/consignment-cli

ENTRYPOINT ["./consignment-cli", "consignment.json"]
CMD ["./consignment-cli"]