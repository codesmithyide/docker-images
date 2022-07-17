FROM gcc:12.1.0

RUN apt-get update
RUN apt-get -y install python-dev

WORKDIR /projects/codesmithyide/Kitware

RUN git clone https://github.com/codesmithyide/Kitware_CMake.git CMake
RUN cd CMake && ./bootstrap && make && make install

WORKDIR /projects

RUN wget https://boostorg.jfrog.io/artifactory/main/release/1.78.0/source/boost_1_78_0.tar.bz2
RUN tar xjf boost_1_78_0.tar.bz2

WORKDIR /projects/boost_1_78_0

RUN ./bootstrap.sh
RUN ./b2 install

WORKDIR /projects/codesmithyide/ishiko/cpp/fmtlib

RUN git clone https://github.com/ishiko-third-party/fmtlib_fmt.git fmt
RUN cd fmt && mkdir build && cd build && cmake .. && make && make install

ENV LIBGIT2=/projects/codesmithyide/libgit2/libgit2
ENV ISHIKO_CPP_THIRD_PARTY_PUGIXML=/codesmithyide/ishiko/cpp/pugixml
ENV ISHIKO_CPP=/codesmithyide/ishiko/cpp
ENV DIPLODOCUSDB=/codesmithyide/diplodocusdb

WORKDIR /projects/codesmithyide/libgit2

RUN git clone https://github.com/codesmithyide/libgit2_libgit2.git libgit2
RUN cd libgit2 && mkdir build && cd build && cmake .. -DBUILD_SHARED_LIBS=OFF -DCMAKE_INSTALL_PREFIX=/projects/codesmithyide/libgit2/libgit2 && cmake --build . && cmake --build . --target install

WORKDIR /codesmithyide/ishiko/cpp

RUN git clone https://github.com/codesmithyide/ishiko-cpp_pugixml.git pugixml

RUN git clone https://github.com/codesmithyide/ishiko-cpp_base-platform.git base-platform
RUN cd base-platform/build/gnumake && make

RUN git clone https://github.com/codesmithyide/ishiko-cpp_errors.git errors
RUN cd errors/build/gnumake && make

RUN git clone https://github.com/codesmithyide/ishiko-cpp_memory.git memory
RUN cd memory/build/gnumake && make

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

RUN git clone https://github.com/codesmithyide/ishiko-cpp_xml.git xml
RUN cd xml/build/gnumake && make

RUN git clone https://github.com/codesmithyide/ishiko-cpp_diff.git diff
RUN cd diff/build/gnumake && make

RUN git clone https://github.com/codesmithyide/ishiko-cpp_configuration.git configuration
RUN cd configuration/build/gnumake && make

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
