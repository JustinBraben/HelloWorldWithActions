# CMakeList.txt : CMake project for HelloWorldWithActions, include source and define
# project specific logic here.
#

cmake_minimum_required(VERSION 3.16)

project(main)

# Add source to this project's executable.
add_executable (main main.cpp)

install (TARGETS main)

enable_testing()
add_test(NAME main COMMAND main)

# TODO: Add tests and install targets if needed.
