cmake_minimum_required (VERSION 3.16)

project(UnitTest)

add_executable(${PROJECT_NAME}
	"test_case/ChooseBetterSignature.cpp"
	"test_case/CustomTypeSerialization.cpp"
	"test_case/PointerTupleConverterSerialization.cpp"
	"test_case/QualifiersErasure.cpp"
	"test_case/SerializationExceptions.cpp"
	"test_case/SimpleTypeSerialization.cpp"
	"test_case/TupleConverterSerialization.cpp"
	"main.cpp")

target_include_directories(${PROJECT_NAME} PRIVATE
  ${CMAKE_CURRENT_SOURCE_DIR}/include
  ${CMAKE_SOURCE_DIR}/third_party/include)

target_precompile_headers(${PROJECT_NAME} PRIVATE "include/pch.h")

target_link_libraries(${PROJECT_NAME} PRIVATE ByteConverter)
