cmake_minimum_required(VERSION 3.5)

project(compression_app)

# #########################################################
# test
#
set(CMAKE_VERBOSE_MAKEFILE ON)
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_BUILD_TYPE Release)
set(CMAKE_CXX_FLAGS_RELEASE "${CMAKE_CXX_FLAGS_RELEASE} -O3")

# Dependency fetching
set(FETCHCONTENT_QUIET OFF)
include(FetchContent)
FetchContent_Declare(
    fmt
    GIT_REPOSITORY https://github.com/fmtlib/fmt.git
    GIT_TAG 11.0.2
    FIND_PACKAGE_ARGS
)
FetchContent_MakeAvailable(fmt)
FetchContent_Declare(
    argparse
    GIT_REPOSITORY https://github.com/p-ranav/argparse
    GIT_TAG 68fd0277eea5412aff9b91c0b70efc698359dae0
)
FetchContent_MakeAvailable(argparse)

# #########################################################
# Paths
#
set(TERSE_INCLUDE_DIR "${CMAKE_CURRENT_SOURCE_DIR}/include")

# #########################################################
# sources/binaries
#
add_subdirectory(src)

# #########################################################
# test
#
add_subdirectory(test)
