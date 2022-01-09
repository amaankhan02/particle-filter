cmake_minimum_required(VERSION 3.8)
project(ParticleFilter)

set(CMAKE_CXX_STANDARD 14)

# FetchContent added in CMake 3.11, downloads during the configure step
include(FetchContent)

# FetchContent_MakeAvailable was not added until CMake 3.14
if(${CMAKE_VERSION} VERSION_LESS 3.14)
    include(cmake/add_FetchContent_MakeAvailable.cmake)
endif()

# Add subdirectories
add_subdirectory(src)
add_subdirectory(apps)