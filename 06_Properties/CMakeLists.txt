cmake_minimum_required(VERSION 3.9...3.22.2)

if(${CMAKE_VERSION} VERSION_LESS 3.12)
    cmake_policy(VERSION ${CMAKE_VERSION})
endif()

project(cmake_tut_06
    VERSION 1.0.0
    DESCRIPTION "This is my project description"
    LANGUAGES CXX
    )

set(SOURCE main.cpp)
set(EXE_NAME cmake_tut_06)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)


add_executable(${EXE_NAME} ${SOURCE})

#save all sources from cmake_tut_06 in TUT_SRCS 
get_property(
    TUT_SRCS
    TARGET cmake_tut_06
    PROPERTY SOURCES
)

get_property(
    CXX_STD
    TARGET cmake_tut_06
    PROPERTY CXX_STANDARD
)

message("${TUT_SRCS}")
message("${CXX_STD}")