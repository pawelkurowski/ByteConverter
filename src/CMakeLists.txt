cmake_minimum_required (VERSION 3.16)

project (ByteConverter)

add_library(${PROJECT_NAME} INTERFACE)
target_include_directories(${PROJECT_NAME} INTERFACE
    $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
    $<INSTALL_INTERFACE:include>
)

target_compile_features(${PROJECT_NAME} INTERFACE cxx_std_20)
if(MSVC)
    target_compile_options(${PROJECT_NAME} INTERFACE /W4 /WX)
else()
    target_compile_options(${PROJECT_NAME} INTERFACE -Wall -Wextra -Wpedantic -Werror -Wno-missing-braces)
endif()

include(GNUInstallDirs)
install(TARGETS ${PROJECT_NAME})
install(DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/include/FSecure
    DESTINATION ${CMAKE_INSTALL_INCLUDEDIR}
)
