FROM ubuntu:latest

RUN apt-get update

RUN apt-get install -y autoconf automake libtool curl make g++ unzip git

RUN mkdir protobuf_src

WORKDIR /protobuf_src

RUN git clone https://github.com/protocolbuffers/protobuf.git

WORKDIR /protobuf_src/protobuf

RUN git submodule update --init --recursive

RUN ./autogen.sh

RUN ./configure

RUN make

RUN make check

RUN make install

RUN ldconfig

RUN apt-get install -y python3.7

RUN apt-get install -y python3-pip

RUN pip3 install protobuf

CMD ["/bin/bash"]
