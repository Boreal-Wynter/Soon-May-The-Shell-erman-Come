cmake_minimum_required(VERSION 3.10)

project(
  result 
  VERSION 1.0 
  LANGUAGE C
)

set(
  SOURCES_DIR
  src/main.c
)

set(
  LIBRARY_DIR 
  lib/util.c
  lib/util.h
)

add_library(project_library STATIC ${LIBRARY_DIR})

add_executable(${PROJECT_NAME} ${SOURCES_DIR})

target_include_directories(project_library PUBLIC lib)

target_link_libraries(${PROJECT_NAME} PRIVATE project_library)
