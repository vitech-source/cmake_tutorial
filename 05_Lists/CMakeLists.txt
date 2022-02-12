cmake_minimum_required(VERSION 3.9...3.22.2)

if(${CMAKE_VERSION} VERSION_LESS 3.12)
    cmake_policy(VERSION ${CMAKE_VERSION})
endif()

project(cmake_tut_05
    VERSION 1.0.0
    DESCRIPTION "This is my project description"
    LANGUAGES CXX
    )

set(SOURCE main.cpp)
set(EXE_NAME cmake_tut_05)

add_executable(${EXE_NAME} ${SOURCE})

set(LIST1 main.cpp myfunc.cpp)
set(LIST2 "main.cpp;myfunc.cpp")
set(LIST3 a b c d e f g h)

#operations on lists
list(LENGTH LIST3 LEN)
list(GET LIST3 1 3 4 5 LISTELEMS)
list(APPEND LIST3 i j)
list(REMOVE_ITEM LIST3 c a)
list(SORT LIST3)


#type of message printouts
message("List 1: ${LIST1}")
message("List 2: " ${LIST2})

#note that cmake will print the final list only
message("Number of elements in LIST3: = ${LEN}")
message("Get list elements by index: " ${LISTELEMS})
message("Append i and j to LIST3: ${LIST3}")
message("Removed c and a from LIST3: ${LIST3}")
message("Alphabetical sort of LIST3: ${LIST3}")
