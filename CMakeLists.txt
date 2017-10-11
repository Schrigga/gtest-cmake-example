cmake_minimum_required(VERSION 3.1)

# Options. Turn on with 'cmake -Dmyvarname=ON'.
option(test "Build all tests." ON) # Makes boolean 'test' available.

# Make PROJECT_SOURCE_DIR, PROJECT_BINARY_DIR, and PROJECT_NAME available.
set(PROJECT_NAME MyProject)
project(${PROJECT_NAME})

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Werror -Wall -g -pedantic -Wextra")
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

################################
# Normal Libraries & Executables
################################
include_directories(include)
add_subdirectory(src)
add_subdirectory(examples)

################################
# Testing
################################
if (test)
  enable_testing()
  add_subdirectory(test)
endif()
