cmake_minimum_required(VERSION 3.17.1)
project(tchem0D)

set(CMAKE_CXX_STANDARD 17)

# Set TChem_DIR and Tines_DIR and Kokkos_DIR
find_package(TChem REQUIRED)
find_package(Tines REQUIRED)
find_package(Kokkos REQUIRED)

add_executable(exe main.cpp)
target_link_libraries(exe TChem::tchem)