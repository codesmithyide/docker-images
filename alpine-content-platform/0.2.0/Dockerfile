FROM nemuframework/alpine-nemu-cpp:0.1.0

ENV CODESMITHYIDE=/codesmithyide

WORKDIR /codesmithyide

RUN git clone https://github.com/codesmithyide/content-platform.git
RUN cd content-platform/core/build/gnumake && make
RUN cd content-platform/web-server/build/gnumake && make

RUN addgroup --gid 1000 codesmithy-content-platform
RUN adduser --uid 1000 --ingroup codesmithy-content-platform --disabled-password codesmithy-content-platform

WORKDIR /

USER codesmithy-content-platform

ENTRYPOINT /codesmithyide/content-platform/web-server/build/gnumake/CodeSmithyContentPlatformWebServer
