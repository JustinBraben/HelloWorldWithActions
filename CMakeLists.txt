cmake_minimum_required(VERSION 3.20)

project(go-cpp CXX)
set(CMAKE_CXX_STANDARD 17)
include_directories(${PROJECT_SOURCE_DIR}/src)

# enable_testing()  # Commented out as there are no tests yet

################################################################################
# Library
################################################################################

# Commented out the goimpl library
# file(GLOB SOURCE_FILES ${PROJECT_SOURCE_DIR}/source/*.cpp)
# list(REMOVE_ITEM SOURCE_FILES ${PROJECT_SOURCE_DIR}/source/main.cpp)
# add_library(goimpl ${SOURCE_FILES})

################################################################################
# Main executable
################################################################################

add_executable(go ${PROJECT_SOURCE_DIR}/src/main.cpp)

# Commented out the target_link_libraries line for goimpl
# target_link_libraries(go goimpl)

################################################################################
# Find and link SFML
################################################################################

find_package(SFML COMPONENTS system window graphics network audio REQUIRED)
target_link_libraries(go sfml-system sfml-window sfml-graphics sfml-network sfml-audio)

################################################################################
# Test executable
################################################################################

# Commented out the test-related commands
# find_package(Catch2 3 CONFIG REQUIRED)

# file(GLOB TEST_SOURCE_FILES ${PROJECT_SOURCE_DIR}/tests/*.cpp)
# add_executable(go-tests ${TEST_SOURCE_FILES})
# target_link_libraries(go-tests PUBLIC goimpl PRIVATE Catch2::Catch2WithMain)

# include(CTest)
# include(Catch)
# catch_discover_tests(go-tests REPORTER junit OUTPUT_DIR junit-output)
