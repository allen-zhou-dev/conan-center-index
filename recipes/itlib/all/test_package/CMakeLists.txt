cmake_minimum_required(VERSION 3.4)
project(test_package)

include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
conan_basic_setup(TARGETS)

find_package(itlib CONFIG REQUIRED)

add_executable(${PROJECT_NAME} test_package.cpp)
target_link_libraries(${PROJECT_NAME} itlib::itlib)
target_compile_features(${PROJECT_NAME} PRIVATE cxx_std_11)
