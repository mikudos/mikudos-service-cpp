# mikudos-service-c++

mikudos-service-c++

# Build with Makefile

please install protobuf and grpc with grpc_cpp_plugin for generate code with the Makefile

# Build with CMake

If you want to use CMake to generate your Makefile for your project. please use cmake to install the protobuf package and the grpc package. You can follow the steps:

1. clone the gRPC package from GitHub `git clone https://github.com/grpc/grpc.git && cd grpc`
2. update all the submodule for gRPC package `git submodule update --init --recursive`
3. Build Protobuf using CMake `cd third_party/protobuf/cmake && cmake . && make && make install`
4. Build gRPC als submodule
    - cd to gRPC directory `cd ../../..`
    - `mkdir build_grpc && cd build_grpc`
    - Config your gRPC as a submodule and use CMake to generate Makefile to build your own gRPC package `cmake -DgRPC_INSTALL=ON -DgRPC_BUILD_TESTS=OFF -DgRPC_PROTOBUF_PROVIDER=package -DgRPC_ZLIB_PROVIDER=package -DgRPC_CARES_PROVIDER=package ..` (I'm use openssl@1.1 and the install folder of openssl with brew install is under that location, please change to your local openssl folder)
    - `make && make install`
5. Congratulations! you can use CMake to build your project now!
