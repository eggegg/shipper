gene:
	protoc -I. --go_out=plugins=micro:$(GOPATH)/src/github.com/eggegg/shipper/consignment-service \
	  proto/consignment/consignment.proto

build:
	protoc -I. --go_out=plugins=micro:$(GOPATH)/src/github.com/eggegg/shipper/consignment-service \
	  proto/consignment/consignment.proto
	GOOS=linux GOARCH=amd64 go build

run:
	docker run -p 50051:50051 \
		-e MICRO_SERVER_ADDRESS=:50051 \
		-e MICRO_REGISTRY=mdns consignment-service