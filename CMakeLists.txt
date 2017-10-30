cmake_minimum_required(VERSION 3.1)
project(TemplateProject)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG} -O0")
set(CMAKE_C_FLAGS_DEBUG "${CMAKE_C_FLAGS_DEBUG} -O0")


add_subdirectory(external/googletest)
enable_testing()
include_directories("${PROJECT_SOURCE_DIR}/external/googletest/googletest/include"
                    "${PROJECT_SOURCE_DIR}/external/googletest/googlemock/include")

add_executable(test1 test1.cpp)
target_link_libraries(test1 gtest gtest_main)
add_test(test1 test1)

add_executable(main main.cpp)
