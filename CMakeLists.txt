cmake_minimum_required (VERSION 2.6)
project (protoc-gen-ue4pb)


set(Protobuf_LIBRARIES "D:/Works/protobuf4/4/src")
set(Protobuf_INCLUDE_DIR "D:/Works/protobuf4/4/src")
set(PROTOBUF_LIBRARY "D:/Works/protobuf4/install/lib/libprotobuf.lib")
set(Protobuf_PROTOC_LIBRARY "D:/Works/protobuf4/install/lib/libprotoc.lib")

include_directories("D:/Works/protobuf4/4/src")

file(GLOB helloworld_SRC
    "*.h"
    "*.cc"
)

add_executable(protoc-gen-ue4pb main.cpp ${helloworld_SRC})

include(FindProtobuf)
find_package(Protobuf REQUIRED)

include_directories(${PROTOBUF_INCLUDE_DIR})
target_link_libraries(protoc-gen-ue4pb
    ${PROTOBUF_LIBRARY}
    ${PROTOBUF_PROTOC_LIBRARY}
)
