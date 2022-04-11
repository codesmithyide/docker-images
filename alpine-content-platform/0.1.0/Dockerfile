FROM nemuframework/alpine-nemu-cpp:0.1.0

WORKDIR /codesmithyide

RUN git clone https://github.com/codesmithyide/content-platform.git
RUN cd content-platform/web-server/build/gnumake && make

WORKDIR /
