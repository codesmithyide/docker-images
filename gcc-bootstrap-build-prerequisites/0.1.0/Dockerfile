FROM ishiko/gcc-boost:11.1.0-1.76.0

ENV LIBGIT2=/codesmithyide/libgit2
ENV PUGIXML=/codesmithyide/ishiko/cpp/pugixml
ENV ISHIKO_CPP=/codesmithyide/ishiko/cpp
ENV DIPLODOCUSDB=/CodeSmithyIDE

WORKDIR /codesmithyide/Kitware

RUN git clone https://github.com/codesmithyide/Kitware-CMake.git CMake
RUN cd CMake && ./bootstrap && make && make install

WORKDIR /codesmithyide

RUN git clone https://github.com/codesmithyide/libgit2.git
RUN cd libgit2 && mkdir build && cd build && cmake .. -DBUILD_SHARED_LIBS=OFF && cmake --build . && cmake --install . --prefix /codesmithyide/libgit2

WORKDIR /codesmithyide/ishiko/cpp

RUN git clone https://github.com/codesmithyide/ishiko-cpp-pugixml.git pugixml

RUN git clone https://github.com/codesmithyide/ishiko-cpp-platform.git platform
RUN cd platform/build/gnumake && make

RUN git clone https://github.com/codesmithyide/ishiko-cpp-errors.git errors
RUN cd errors/build/gnumake && make

RUN git clone https://github.com/codesmithyide/ishiko-cpp-types.git types
RUN cd types/build/gnumake && make

RUN git clone https://github.com/codesmithyide/ishiko-cpp-collections.git collections
RUN cd collections/build/gnumake && make

RUN git clone https://github.com/codesmithyide/ishiko-cpp-text.git text
RUN cd text/build/gnumake && make

RUN git clone https://github.com/codesmithyide/ishiko-cpp-process.git process
RUN cd process/build/gnumake && make

RUN git clone https://github.com/codesmithyide/ishiko-cpp-filesystem.git filesystem
RUN cd filesystem/build/gnumake && make

RUN git clone https://github.com/codesmithyide/ishiko-cpp-diff.git diff
RUN cd diff/build/gnumake && make

RUN git clone https://github.com/codesmithyide/ishiko-cpp-tests.git tests
RUN cd tests/build/gnumake && make

RUN git clone https://github.com/CodeSmithyIDE/Terminal.git
RUN cd Terminal/Makefiles/GNUmakefile && make

RUN git clone https://github.com/CodeSmithyIDE/Tasks.git
RUN cd Tasks/Makefiles/GNUmakefile && make

RUN git clone https://github.com/CodeSmithyIDE/UUIDs.git
RUN cd UUIDs/Makefiles/GNUmakefile && make

RUN git clone https://github.com/CodeSmithyIDE/Core.git
RUN cd Core/Makefiles/GNUmakefile && make

RUN git clone https://github.com/CodeSmithyIDE/TreeDB.git
RUN cd TreeDB/Core/Makefiles/GNUmakefile && make
RUN cd TreeDB/XMLTreeDB/Makefiles/GNUmakefile && make

WORKDIR /
