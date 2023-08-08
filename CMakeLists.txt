cmake_minimum_required (VERSION 3.16)

project (ByteConverter)

add_subdirectory("src")
add_subdirectory("example")

include(CTest)
add_subdirectory ("test")

