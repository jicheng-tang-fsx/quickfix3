cmake_minimum_required(VERSION 3.0 FATAL_ERROR)

set(quickfix_PROJECT_NAME quickfix)

project(${quickfix_PROJECT_NAME} VERSION 0.1 LANGUAGES CXX C)
message("-- Project name ${CMAKE_PROJECT_NAME}")

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED OFF)

if( CMAKE_CXX_STANDARD EQUAL 17 )
  option( HAVE_CXX17 "Using C++17" ON)
endif()

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${CMAKE_CURRENT_SOURCE_DIR}/cmake/")

include(QuickfixPlatformSettings)

add_subdirectory(src)

configure_file(cmake_config.h.in ${CMAKE_CURRENT_SOURCE_DIR}/src/C++/config.h @ONLY)
configure_file(cmake_config.h.in ${CMAKE_CURRENT_SOURCE_DIR}/include/quickfix/config.h @ONLY)
file(REMOVE config.h)


configure_file(cmake_config.h.in ${CMAKE_CURRENT_SOURCE_DIR}/include/quickfix/config.h @ONLY)

install(DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/spec/ DESTINATION share/quickfix FILES_MATCHING PATTERN "FIX*.xml")
 