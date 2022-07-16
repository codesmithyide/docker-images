FROM diplodocusdb/gcc-diplodocusdb:0.21.0

ENV LIBGIT2=/codesmithyide/libgit2

WORKDIR /codesmithyide/Kitware

RUN git clone https://github.com/codesmithyide/Kitware_CMake.git CMake
RUN cd CMake && ./bootstrap && make && make install

WORKDIR /codesmithyide

RUN git clone https://github.com/codesmithyide/libgit2_libgit2.git libgit2
RUN cd libgit2 && mkdir build && cd build && cmake .. -DBUILD_SHARED_LIBS=OFF && cmake --build . && cmake --install . --prefix /codesmithyide/libgit2

WORKDIR /
