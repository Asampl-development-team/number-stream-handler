cmake_minimum_required(VERSION 3.0.0)

project(number-stream-handler)

if (CMAKE_SOURCE_DIR STREQUAL PROJECT_SOURCE_DIR)
    add_subdirectory(deps/Asampl)
endif()

set(CMAKE_CXX_STANDARD 17)
file(GLOB HANDLER_SRCS src/*.cpp)

add_compile_options(-g)

add_library(number-stream-handler SHARED ${HANDLER_SRCS})
target_link_libraries(number-stream-handler PRIVATE asampl-interface)
