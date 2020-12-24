cmake_minimum_required(VERSION 3.12.4 FATAL_ERROR)

project(ExampleExternal)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)

include(FetchContent)
FetchContent_Declare(
  bbe
  GIT_REPOSITORY https://github.com/Brotcrunsher/BrotboxEngine
  GIT_TAG        v0.1.6
)
FetchContent_GetProperties(bbe)
if(NOT bbe_POPULATED)
  FetchContent_Populate(bbe)
endif()

add_subdirectory(${bbe_SOURCE_DIR} ${bbe_BINARY_DIR})
add_trivial_project(ExampleExternal)