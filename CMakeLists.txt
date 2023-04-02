cmake_minimum_required(VERSION 3.10)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/bin")

project(CXXProgrammingLang
    VERSION 1.0
    LANGUAGES C CXX
)

if (${CMAKE_SOURCE_DIR} STREQUAL ${CMAKE_BINARY_DIR})
    message(FATAL_ERROR "Please do out-of-source builds."
        "Cleanup: \"rm -rf CMake CMakeCache.txt CMakeFiles/\"")
endif()

add_subdirectory(src)
