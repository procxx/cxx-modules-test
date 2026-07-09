cmake_minimum_required(VERSION 3.28)
project(graphon-consumer)

set(CMAKE_CXX_STANDARD 23)
find_package(graphon REQUIRED)

add_executable(app main.cpp)
target_link_libraries(app graphon::graphon)
