[![language.badge]][language.url] [![license.badge]][license.url]

# ClangFormat.cmake module

ClangFormat.cmake is a simple CMake module for clang-format support.

## Requirements

The module requires CMake 3.0 or higher and some version of clang-format
installed.

## Integration

1. Obtain the module and add it into your project's CMake modules path:

   * Copy approach:

     ```bash
     $ wget https://raw.githubusercontent.com/zemasoft/clangformat-cmake/master/cmake/ClangFormat.cmake -P cmake
     ```

     ```cmake
     # CMakeLists.txt

     list(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/cmake)
     ```

   * Submodule approach:

     ```bash
     $ git submodule add https://github.com/zemasoft/clangformat-cmake
     ```

     ```cmake
     # CMakeLists.txt

     list(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/clangformat-cmake/cmake)
     ```

2. Include the module:

   ```cmake
   # CMakeLists.txt

   include(ClangFormat)
   ```

3. Setup the module:

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
   $ cmake -S . -Bbuild
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

[language.url]:   https://cmake.org/
[language.badge]: https://img.shields.io/badge/language-CMake-blue.svg

[license.url]:    http://www.boost.org/LICENSE_1_0.txt
[license.badge]:  https://img.shields.io/badge/license-Boost%201.0-blue.svg
