
LOCAL_PATH = $(GOPATH)/src/github.com/googleapis/gnostic/extensions/sample/generated

build:
	go get github.com/golang/protobuf/protoc-gen-go
	cd ..; ./COMPILE-EXTENSION.sh
	generate-gnostic --extension x-sampleone.json --out_dir=$(LOCAL_PATH)
	cd $(LOCAL_PATH)/gnostic-x-sampleone/proto && protoc --go_out=Mgoogle/protobuf/any.proto=github.com/golang/protobuf/ptypes/any:. *.proto
	cd $(LOCAL_PATH)/gnostic-x-sampleone && go get && go install
	generate-gnostic --extension x-sampletwo.json --out_dir=$(LOCAL_PATH)
	cd $(LOCAL_PATH)/gnostic-x-sampletwo/proto && protoc --go_out=Mgoogle/protobuf/any.proto=github.com/golang/protobuf/ptypes/any:. *.proto
	cd $(LOCAL_PATH)/gnostic-x-sampletwo && go get && go install
