# clangformat-cmake

```cmake
cmake_minimum_required(VERSION 2.8)
project(myproject)

# Add project's cmake modules to path
set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} ${PROJECT_SOURCE_DIR}/cmake)

option(CLANGFORMAT "Setup clangformat target" ON)

if(CLANGFORMAT)
  include(ClangFormat)

  # List sources to format
  set(clangformat_srcs include/header.hpp
                       src/source.cpp)

  # Setup clangformat target
  clangformat_setup("${clangformat_srcs}")
endif()

... # Setup the rest of the project
```

```bash
$ cmake . -Bbuild
$ cmake --build build/ --target clangformat
```
