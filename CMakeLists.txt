cmake_minimum_required(VERSION 3.1)

project(tarantool-cpp)

# BOOST
find_package(Boost 1.67.0 COMPONENTS system iostreams)
include_directories(${Boost_INCLUDE_DIRS})

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED on)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -Winline")

add_executable(tests test.cpp)

target_link_libraries(tests tarantool ${Boost_LIBRARIES})
