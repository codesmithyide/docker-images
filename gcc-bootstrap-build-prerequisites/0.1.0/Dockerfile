FROM ishikocpp/gcc-boost:10.1.0-1.73.0

ENV LIBGIT2=/libgit2

RUN git clone https://github.com/CodeSmithyIDE/CMake.git
RUN cd /CMake && ./bootstrap && make && make install

RUN git clone https://github.com/CodeSmithyIDE/libgit2.git
RUN cd libgit2 && mkdir build && cd build && cmake .. -DBUILD_SHARED_LIBS=OFF && cmake --build .
