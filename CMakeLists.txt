cmake_minimum_required(VERSION 3.10)
project(Retail C)

set(SRC_DIR "${CMAKE_SOURCE_DIR}/src")
set(TESTS_DIR "${CMAKE_SOURCE_DIR}/tests")

include_directories(${SRC_DIR})

file(GLOB_RECURSE SOURCES "${SRC_DIR}/*.c" "${SRC_DIR}/*.h")

add_executable(Retail ${SOURCES})

find_package(Criterion QUIET)


file(GLOB_RECURSE TEST_SOURCES "${TESTS_DIR}/*.c")

add_executable(tests ${TEST_SOURCES})
target_link_libraries(tests Criterion::Criterion)
