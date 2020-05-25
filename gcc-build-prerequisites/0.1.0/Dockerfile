FROM diplodocusdb/gcc-diplodocusdb:0.1.0

WORKDIR /CMake
RUN git clone hhttps://github.com/CodeSmithyIDE/CMake.git
RUN ./bootstrap && make && make install

WORKDIR /
