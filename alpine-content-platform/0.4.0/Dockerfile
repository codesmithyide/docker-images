FROM nemuframework/alpine-nemu-cpp:0.5.0 as build

ENV CODESMITHYIDE=/codesmithyide

WORKDIR /codesmithyide

RUN git clone https://github.com/codesmithyide/content-platform.git
RUN cd content-platform/core/build/gnumake && make
RUN cd content-platform/web-server/build/gnumake && make

RUN git clone https://github.com/codesmithyide/content-platform-themes.git

FROM alpine:3.15.4

RUN apk add libgcc
RUN apk add libstdc++
RUN apk add boost1.77-filesystem

RUN addgroup --gid 1000 codesmithy-content-platform
RUN adduser --uid 1000 --ingroup codesmithy-content-platform --disabled-password codesmithy-content-platform

USER codesmithy-content-platform

COPY --from=build /codesmithyide/content-platform/web-server/build/gnumake/CodeSmithyContentPlatformWebServer /usr/local/bin/CodeSmithyContentPlatformWebServer
COPY --from=build /codesmithyide/content-platform-themes /codesmithyide/content-platform-themes

ENV CODESMITHYIDE=/codesmithyide 

ENTRYPOINT /usr/local/bin/CodeSmithyContentPlatformWebServer
