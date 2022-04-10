FROM ishiko/gcc-ishiko-cpp:0.22.0

ENV LIBGIT2=/codesmithyide/libgit2
ENV ISHIKO_CPP_THIRD_PARTY_PUGIXML=/codesmithyide/ishiko/cpp/pugixml
ENV ISHIKO_CPP=/codesmithyide/ishiko/cpp
ENV DIPLODOCUSDB=/codesmithyide/diplodocusdb

WORKDIR /codesmithyide/Kitware

RUN git clone https://github.com/codesmithyide/Kitware_CMake.git CMake
RUN cd CMake && ./bootstrap && make && make install

WORKDIR /codesmithyide

RUN git clone https://github.com/codesmithyide/libgit2.git
RUN cd libgit2 && mkdir build && cd build && cmake .. -DBUILD_SHARED_LIBS=OFF && cmake --build . && cmake --install . --prefix /codesmithyide/libgit2

WORKDIR /codesmithyide/ishiko/cpp

RUN git clone https://github.com/codesmithyide/ishiko-cpp_pugixml.git pugixml

RUN git clone https://github.com/codesmithyide/ishiko-cpp_base-platform.git base-platform
RUN cd base-platform/build/gnumake && make

RUN git clone https://github.com/codesmithyide/ishiko-cpp_errors.git errors
RUN cd errors/build/gnumake && make

RUN git clone https://github.com/codesmithyide/ishiko-cpp_types.git types
RUN cd types/build/gnumake && make

RUN git clone https://github.com/codesmithyide/ishiko-cpp_collections.git collections
RUN cd collections/build/gnumake && make

RUN git clone https://github.com/codesmithyide/ishiko-cpp_text.git text
RUN cd text/build/gnumake && make

RUN git clone https://github.com/codesmithyide/ishiko-cpp_time.git time
RUN cd time/build/gnumake && make

RUN git clone https://github.com/codesmithyide/ishiko-cpp_process.git process
RUN cd process/build/gnumake && make

RUN git clone https://github.com/codesmithyide/ishiko-cpp_filesystem.git filesystem
RUN cd filesystem/build/gnumake && make

RUN git clone https://github.com/codesmithyide/ishiko-cpp_diff.git diff
RUN cd diff/build/gnumake && make

RUN git clone https://github.com/codesmithyide/ishiko-cpp_test-framework.git test-framework
RUN cd test-framework/core/build/gnumake && make
RUN cd test-framework/build/gnumake && make

RUN git clone https://github.com/codesmithyide/ishiko-cpp_terminal.git terminal
RUN cd terminal/build/gnumake && make

RUN git clone https://github.com/codesmithyide/ishiko-cpp_user-tasks.git user-tasks
RUN cd user-tasks/build/gnumake && make

RUN git clone https://github.com/codesmithyide/ishiko-cpp_uuids.git uuids
RUN cd uuids/build/gnumake && make

WORKDIR /codesmithyide/diplodocusdb

RUN git clone https://github.com/codesmithyide/diplodocusdb_core.git core
RUN cd core/build/gnumake && make

RUN git clone https://github.com/codesmithyide/diplodocusdb_tree-db.git tree-db
RUN cd tree-db/core/build/gnumake && make
RUN cd tree-db/xml-tree-db/build/gnumake && make

WORKDIR /
