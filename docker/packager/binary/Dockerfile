FROM ubuntu:18.04

RUN echo "deb [trusted=yes] http://apt.llvm.org/bionic/ llvm-toolchain-bionic-7 main" >> /etc/apt/sources.list

RUN apt-get update -y \
    && env DEBIAN_FRONTEND=noninteractive \
        apt-get install --yes --no-install-recommends \
            bash \
            cmake \
            curl \
            gcc-7 \
            g++-7 \
            gcc-8 \
            g++-8 \
            clang-6.0 \
            lld-6.0 \
            libclang-6.0-dev \
            liblld-6.0-dev \
            llvm-6.0 \
            libllvm6.0 \
            llvm-6.0-dev \
            clang-7 \
            lld-7 \
            libclang-7-dev \
            liblld-7-dev \
            llvm-7 \
            libllvm7 \
            llvm-7-dev \
            libicu-dev \
            libreadline-dev \
            ninja-build \
            git

CMD mkdir -p build/build_result && cd build/build_result && cmake .. -DCMAKE_BUILD_TYPE=$BUILD_TYPE -DSANITIZE=$SANITIZER && ninja && mv ./dbms/programs/clickhouse* /output
