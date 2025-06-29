cmake_minimum_required(VERSION 3.31)
project(raylib_project)

set(CMAKE_CXX_STANDARD 20)

add_subdirectory(external/raylib-5.5)
include_directories(external/raylib-5.5/src)

#Define SOURCES as a list of every .cpp that I'm using
file(GLOB_RECURSE SOURCES CONFIGURE_DEPENDS "${CMAKE_CURRENT_SOURCE_DIR}/src/*.cpp")

add_executable(raylib_project "${SOURCES}")

target_link_libraries(raylib_project PRIVATE raylib)
#target_compile_definitions("${CMAKE_PROJECT_NAME}" PUBLIC RESOURCES_PATH="${CMAKE_CURRENT_SOURCE_DIR}/resources/")
#target_include_directories("${CMAKE_PROJECT_NAME}" PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}/include/")