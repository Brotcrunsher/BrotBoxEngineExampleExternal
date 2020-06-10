cmake_minimum_required(VERSION 3.12.4 FATAL_ERROR)

project(ExampleExternal)

include(FetchContent)
FetchContent_Declare(
  bbe
  GIT_REPOSITORY https://github.com/Brotcrunsher/BrotboxEngine
  GIT_TAG        v0.1.1
)
FetchContent_GetProperties(bbe)
if(NOT bbe_POPULATED)
  FetchContent_Populate(bbe)
endif()

add_subdirectory(${bbe_SOURCE_DIR} ${bbe_BINARY_DIR})
add_trivial_project(ExampleExternal)