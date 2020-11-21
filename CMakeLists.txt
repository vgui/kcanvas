cmake_minimum_required(VERSION 2.8)

project(kcanvas_package)

include_directories(include)

set(MyApp_BINARY_DIR ${PROJECT_BINARY_DIR}/bin-${CMAKE_BUILD_TYPE})
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${MyApp_BINARY_DIR})
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${MyApp_BINARY_DIR})
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${MyApp_BINARY_DIR})

add_subdirectory(src)
add_subdirectory(examples)
