cmake_minimum_required(VERSION 3.0 FATAL_ERROR)

set(quickfix_PROJECT_NAME quickfix)

project(${quickfix_PROJECT_NAME} VERSION 0.1 LANGUAGES CXX C)
message("-- Project name ${CMAKE_PROJECT_NAME}")

# set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -Wextra -Wconversion -Wpedantic -Wshadow ")
# set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wformat -Wsign-compare -Wundef ")
# set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wfloat-equal -Wredundant-decls ")

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -g -O3 -std=gnu++17 ")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -static-libstdc++ -static-libgcc ")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -ffunction-sections -fdata-sections ")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -flto=8 ")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -march=native -mtune=native ")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wno-deprecated-declarations ")

add_subdirectory(src/C++) 