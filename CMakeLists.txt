cmake_minimum_required (VERSION 3.1) 
project(OpenGex)
set (CMAKE_C_STANDARD 99)
set (CMAKE_CXX_STANDARD 11)

IF(${UNIX})
    set(MYGE_TARGET_PLATFORM "Linux")
ELSEIF(${WIN32})
    set(MYGE_TARGET_PLATFORM "Windows")
ENDIF(${UNIX})

add_subdirectory(OpenDDL)
add_subdirectory(OpenGEX)

