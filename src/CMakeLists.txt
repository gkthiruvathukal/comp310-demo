project("pthreads")

cmake_minimum_required(VERSION 2.6)

# https://stackoverflow.com/questions/6594796/how-do-i-make-cmake-output-into-a-bin-dir
# We only need 'bin' here.

if (CMAKE_VERSION VERSION_LESS "3.1")
  add_definitions(-std=c++11)
else()
  set(CMAKE_CXX_STANDARD 11)
  set(CMAKE_CXX_STANDARD_REQUIRED ON)
  set(CMAKE_CXX_EXTENSIONS OFF)
endif()

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)
#set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)
#set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)
 
# Locate GTest
#find_package(GTest REQUIRED)
#include_directories(${GTEST_INCLUDE_DIRS})
 
# Link runTests with what we want to test and the GTest and pthread library
#add_executable(word_main word_main.cc word_entry.cc)

#add_executable(word_entry_tests word_entry_tests.cc word_entry.cc)
#target_link_libraries(word_entry_tests ${GTEST_LIBRARIES} pthread)
#
#add_executable(word_entry_dry_tests word_entry_dry_tests.cc word_entry.cc)
#target_link_libraries(word_entry_dry_tests ${GTEST_LIBRARIES} pthread)

add_executable(llnl1 llnl1.c)
target_link_libraries(llnl1 pthread)

add_executable(llnl2 llnl2.c)
target_link_libraries(llnl2 pthread)

add_executable(llnl_cv1 llnl_cv1.c)
target_link_libraries(llnl_cv1 pthread)

add_executable(strbuffer_demo strbuffer_demo.c strbuffer.c)

add_executable(getline_demo getline_demo.c strbuffer.c)
