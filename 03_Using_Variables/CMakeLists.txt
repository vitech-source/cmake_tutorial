cmake_minimum_required(VERSION 3.9...3.22.2)

if(${CMAKE_VERSION} VERSION_LESS 3.12)
    cmake_policy(VERSION ${CMAKE_VERSION})
endif()

project(cmake_tut_03
    VERSION 1.0.0
    DESCRIPTION "This is my project description"
    LANGUAGES CXX
    )

set(SOURCE main.cpp)
set(EXE_NAME cmake_tut_03)

add_executable(${EXE_NAME} ${SOURCE})

unset(SOURCE)
set(EXE_NAME)