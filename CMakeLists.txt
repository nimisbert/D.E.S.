# Project :
cmake_minimum_required(VERSION 3.22.1)
project(cryptography)
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Wall")
include_directories(include)

# Libraries :

add_library(des SHARED
    src/bitset.c
    src/des.c
    src/box.c
)

# Executables :
add_executable(bitset-test tests/bitset-test.c)
target_link_libraries(bitset-test des)

add_executable(des-test tests/des-test.c)
target_link_libraries(des-test des)
