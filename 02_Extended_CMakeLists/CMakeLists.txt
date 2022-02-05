cmake_minimum_required(VERSION 3.9...3.22.2)

if(${CMAKE_VERSION} VERSION_LESS 3.12)
    cmake_policy(VERSION ${CMAKE_VERSION})
endif()

project(cmake_tut_02
    VERSION 1.0.0
    DESCRIPTION "This is my project description"
    LANGUAGES CXX
    )

add_executable(cmake_tut_02 main.cpp)