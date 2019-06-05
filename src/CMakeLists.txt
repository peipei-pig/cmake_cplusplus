
PROJECT(CMAKEDEMO)
#set Debug and Release mode
if(CMAKE_BUILD_TYPE STREQUAL "Debug")
    SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11 -g -Wall -fPIC -O0")
else()
    SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11 -Wall -fPIC -O3")
endif()

#set DIR include source file
SET(HELLO_SRCS
    hello/helloTest.cpp
)

#set .so named libHello.so
ADD_LIBRARY(Hello SHARED ${HELLO_SRCS})

#set .a named  libHello.a
ADD_LIBRARY(Hello_Static STATIC ${HELLO_SRCS})

#set link library
#TARGET_LINK_LIBRARIES(CXX XX libxx.a)

#set clean library
SET_TARGET_PROPERTIES(Hello PROPERTIES CLEAN_DIRECT_OUTPUT 1)
SET_TARGET_PROPERTIES(Hello_static PROPERTIES CLEAN_DIRECT_OUTPUT 1)

