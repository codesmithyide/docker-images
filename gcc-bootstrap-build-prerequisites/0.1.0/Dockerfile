FROM ishikocpp/gcc-boost:10.1.0-1.73.0

ENV PUGIXML=/CodeSmithyIDE/pugixml
ENV LIBGIT2=/CodeSmithyIDE/libgit2
ENV ISHIKO_CPP=/CodeSmithyIDE
ENV DIPLODOCUSDB=/CodeSmithyIDE

WORKDIR /CodeSmithyIDE

RUN git clone https://github.com/CodeSmithyIDE/CMake.git
RUN cd CMake && ./bootstrap && make && make install

RUN git clone https://github.com/CodeSmithyIDE/pugixml.git

RUN git clone https://github.com/CodeSmithyIDE/libgit2.git
RUN cd libgit2 && mkdir build && cd build && cmake .. -DBUILD_SHARED_LIBS=OFF && cmake --build . && cmake --install . --prefix /CodeSmithyIDE/libgit2

RUN git clone https://github.com/CodeSmithyIDE/Errors.git
RUN cd Errors/Makefiles/GNUmakefile && make

RUN git clone https://github.com/CodeSmithyIDE/Types.git
RUN cd Types/Makefiles/GNUmakefile && make

RUN git clone https://github.com/CodeSmithyIDE/Process.git
RUN cd Process/Makefiles/GNUmakefile && make

RUN git clone https://github.com/CodeSmithyIDE/TestFramework.git
RUN cd TestFramework/Core/Makefiles/GNUmakefile && make

RUN git clone https://github.com/CodeSmithyIDE/Collections.git
RUN cd Collections/Makefiles/GNUmakefile && make

RUN git clone https://github.com/CodeSmithyIDE/FileSystem.git
RUN cd FileSystem/Makefiles/GNUmakefile && make

RUN git clone https://github.com/CodeSmithyIDE/Terminal.git
RUN cd Terminal/Makefiles/GNUmakefile && make

RUN git clone https://github.com/CodeSmithyIDE/Tasks.git
RUN cd Tasks/Makefiles/GNUmakefile && make

RUN git clone https://github.com/CodeSmithyIDE/Core.git
RUN cd Core/Makefiles/GNUmakefile && make

RUN git clone https://github.com/CodeSmithyIDE/TreeDB.git
RUN cd TreeDB/Core/Makefiles/GNUmakefile && make
RUN cd TreeDB/XMLTreeDB/Makefiles/GNUmakefile && make

WORKDIR /
