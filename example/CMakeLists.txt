cmake_minimum_required(VERSION 3.16)

project(Example)

add_executable(${PROJECT_NAME} example.cpp)
target_compile_features(${PROJECT_NAME} PRIVATE cxx_std_17)

target_link_libraries(${PROJECT_NAME} PRIVATE ByteConverter)
