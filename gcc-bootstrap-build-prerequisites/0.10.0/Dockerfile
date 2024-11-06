FROM gcc:14.2.0

WORKDIR /projects/codesmithyide/Kitware

RUN git clone https://github.com/codesmithyide/Kitware_CMake.git CMake
RUN cd CMake && ./bootstrap && make && make install

WORKDIR /projects

RUN wget https://boostorg.jfrog.io/artifactory/main/release/1.86.0/source/boost_1_86_0.tar.bz2
RUN tar xjf boost_1_86_0.tar.bz2

WORKDIR /projects/boost_1_86_0

RUN ./bootstrap.sh --prefix=/usr/local
RUN ./b2 install
RUN ldconfig

WORKDIR /projects/codesmithyide/ishiko/cpp/fmtlib

RUN git clone https://github.com/ishiko-third-party/fmtlib_fmt.git fmt
RUN cd fmt && mkdir build && cd build && cmake .. && make && make install

ENV LIBGIT2=/projects/codesmithyide/libgit2/libgit2
ENV PUGIXML_ROOT=/codesmithyide/ishiko/cpp/pugixml
ENV ISHIKO_CPP_ROOT=/codesmithyide/ishiko/cpp
ENV DIPLODOCUSDB_ROOT=/codesmithyide/diplodocusdb

WORKDIR /projects/codesmithyide/libgit2

RUN git clone https://github.com/codesmithyide/libgit2_libgit2.git libgit2
RUN cd libgit2 && mkdir build && cd build && cmake .. -DBUILD_SHARED_LIBS=OFF -DCMAKE_INSTALL_PREFIX=/projects/codesmithyide/libgit2/libgit2 && cmake --build . && cmake --build . --target install

WORKDIR /codesmithyide/ishiko/cpp

RUN git clone https://github.com/codesmithyide/ishiko-cpp_pugixml.git pugixml

RUN git clone https://github.com/codesmithyide/ishiko-cpp_base-platform.git base-platform
RUN cd base-platform/build-files/gnumake && make

RUN git clone https://github.com/codesmithyide/ishiko-cpp_errors.git errors
RUN cd errors/build-files/gnumake && make

RUN git clone https://github.com/codesmithyide/ishiko-cpp_memory.git memory
RUN cd memory/build-files/gnumake && make

RUN git clone https://github.com/codesmithyide/ishiko-cpp_types.git types
RUN cd types/build-files/gnumake && make

RUN git clone https://github.com/codesmithyide/ishiko-cpp_collections.git collections
RUN cd collections/build-files/gnumake && make

RUN git clone https://github.com/codesmithyide/ishiko-cpp_text.git text
RUN cd text/build-files/gnumake && make

RUN git clone https://github.com/codesmithyide/ishiko-cpp_time.git time
RUN cd time/build-files/gnumake && make

RUN git clone https://github.com/codesmithyide/ishiko-cpp_process.git process
RUN cd process/build-files/gnumake && make

RUN git clone https://github.com/codesmithyide/ishiko-cpp_io.git io
RUN cd io/build-files/gnumake && make

RUN git clone https://github.com/codesmithyide/ishiko-cpp_filesystem.git filesystem
RUN cd filesystem/build-files/gnumake && make

RUN git clone https://github.com/codesmithyide/ishiko-cpp_xml.git xml
RUN cd xml/build-files/gnumake && make

RUN git clone https://github.com/codesmithyide/ishiko-cpp_diff.git diff
RUN cd diff/build-files/gnumake && make

RUN git clone https://github.com/codesmithyide/ishiko-cpp_configuration.git configuration
RUN cd configuration/build-files/gnumake && make

RUN git clone https://github.com/codesmithyide/ishiko-cpp_test-framework.git test-framework
RUN cd test-framework/core/build-files/gnumake && make
RUN cd test-framework/build-files/gnumake && make

RUN git clone https://github.com/codesmithyide/ishiko-cpp_terminal.git terminal
RUN cd terminal/build-files/gnumake && make

RUN git clone https://github.com/codesmithyide/ishiko-cpp_workflows.git workflows
RUN cd workflows/build-files/gnumake && make

RUN git clone https://github.com/codesmithyide/ishiko-cpp_uuids.git uuids
RUN cd uuids/build-files/gnumake && make

WORKDIR /codesmithyide/diplodocusdb

RUN git clone https://github.com/codesmithyide/diplodocusdb_core.git core
RUN cd core/build-files/gnumake && make

RUN git clone https://github.com/codesmithyide/diplodocusdb_physical-storage.git physical-storage
RUN cd physical-storage/build-files/gnumake && make

RUN git clone https://github.com/codesmithyide/diplodocusdb_embedded-document-db.git embedded-document-db
RUN cd embedded-document-db/storage-engine/build-files/gnumake && make
RUN cd embedded-document-db/database/build-files/gnumake && make

WORKDIR /
