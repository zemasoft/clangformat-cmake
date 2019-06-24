[![Language](https://img.shields.io/badge/language-CMake-blue.svg)](https://cmake.org/)
[![Licence](https://img.shields.io/badge/license-Boost%201.0-blue.svg)](http://www.boost.org/LICENSE_1_0.txt)

# ClangFormat CMake module

ClangFormat is a simple CMake module for clang-format support.

## Requirements

The module requires CMake 3.0 or higher and some version of clang-format
installed.

## Integration

1. Obtain the module:

   Copy [`ClangFormat.cmake`](cmake/ClangFormat.cmake) to your project's
   CMake modules directory. Usually to `${PROJECT_SOURCE_DIR}/cmake`.
   
   Or use this project as a submodule with
   `$ git submodule add https://github.com/zemasoft/clangformat-cmake`.
   
2. Add the module's path to your project's CMake modules path:

   ```cmake
   # CMakeLists.txt
   
   list(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/cmake)
   ```

   or:

   ```cmake
   # CMakeLists.txt
   
   list(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/clangformat-cmake/cmake)
   ```

3. Include the module:

   ```cmake
   # CMakeLists.txt
   
   include(ClangFormat)
   ```

4. Setup the module:

   ```cmake
   # CMakeLists.txt
   
   clangformat_setup(
     src/hello.hpp
     src/hello.cpp
   )
   ```

   or:

   ```cmake
   # CMakeLists.txt
   
   target_clangformat_setup(sometarget)
   ```

## Usage

1. Generate the build system:

   ```bash
   $ cmake . -Bbuild
   ```

2. Format sources anytime using `clangformat` target:

   ```bash
   $ cmake --build build --target clangformat
   ```

   or:

   ```bash
   $ cd build
   $ make clangformat
   ```

## Example

See an example [here](https://github.com/zemasoft/clangformat-cmake-example).
