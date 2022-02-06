cmake_minimum_required(VERSION 3.9...3.22.2)

if(${CMAKE_VERSION} VERSION_LESS 3.12)
    cmake_policy(VERSION ${CMAKE_VERSION})
endif()

project(cmake_tut_04
    VERSION 1.0.0
    DESCRIPTION "This is my project description"
    LANGUAGES CXX
    )

set(SOURCE main.cpp)
set(EXE_NAME cmake_tut_04)

add_executable(${EXE_NAME} ${SOURCE})

#possible types: BOOL, FILEPATH, PATH, STRING, INTERNAL
set(BUILD_SECOND_EXE FALSE
    CACHE BOOL 
    "Creates a second EXE")

if(${BUILD_SECOND_EXE})
    add_executable(${EXE_NAME}_2 ${SOURCE})
endif()

set(CACHE_PATH ""
    CACHE PATH
    "Example for a path cache variable")

set(CACHE_INTERNAL ""
    CACHE INTERNAL
    "Example for a internal cache variable"
    FORCE)

set(CACHE_STRING ""
    CACHE STRING
    "Example for a string cache variable")

set_property(CACHE CACHE_STRING
    PROPERTY STRINGS
    selection1 selection2 selection3)

unset(SOURCE)
set(EXE_NAME)