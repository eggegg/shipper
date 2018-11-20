gene:
	protoc -I. --go_out=plugins=micro:$(GOPATH)/src/github.com/eggegg/shipper/vessel-service \
		proto/vessel/vessel.proto

build:
	protoc -I. --go_out=plugins=micro:$(GOPATH)/src/github.com/eggegg/shipper/vessel-service \
		proto/vessel/vessel.proto
	docker build -t vessel-service .

run:
	docker run -p 50052:50051 -e MICRO_SERVER_ADDRESS=:50051 -e MICRO_REGISTRY=mdns vessel-service
