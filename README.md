[![Language](https://img.shields.io/badge/language-CMake-blue.svg)](https://cmake.org/)
[![Licence](https://img.shields.io/badge/license-Boost%201.0-blue.svg)](http://www.boost.org/LICENSE_1_0.txt)

Introduction
============

A simple CMake module for clang-format support.

Requirements
============

The module requires CMake 3.0 or higher and some version of clang-format
installed.

Usage
=====

1. Copy [`ClangFormat.cmake`](cmake/ClangFormat.cmake) to your project's
   CMakeModules directory. Usually to `${PROJECT_SOURCE_DIR}/cmake`.

2. Configure your project's `CMakeLists.txt`.

```cmake
# Add project's cmake modules to path
list(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/cmake)

# Include the module
include(ClangFormat)

# Setup clangformat target
clangformat_setup(
  include/header.hpp
  src/source.cpp
)
```

3. Format using `clangformat` target.

```bash
$ cmake . -Bbuild
$ cmake --build build/ --target clangformat
```

Example
=======

Please see an example [here](https://github.com/zemasoft/clangformat-cmake-example).
