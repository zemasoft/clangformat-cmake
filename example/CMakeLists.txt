cmake_minimum_required(VERSION 3.10)
project(example-clang-format-cmake)

include(../cmake/ClangFormat.cmake)

add_Executable(${PROJECT_NAME} main.cpp)

# Set the following to ON to abort CMake's configuration process if clang-format could not be found.
# On default, it will just emit a status message and continue without creating the clangformat target.
set(CLANGFORMAT_FORCED OFF)
target_clangformat_setup(${PROJECT_NAME})

