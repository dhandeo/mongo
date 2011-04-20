cmake_minimum_required(VERSION 2.8.4)

#Find boost libraries
find_path(BOOST_INCLUDE_DIRECTORIES
	NAMES boost/any.hpp
	PATHS
	 	# Add your favorite boost location here
		c:/boost
		c:/boost/include
		"c:/Program Files/boost"
		"c:/Program Files/boost/include"
		NO_DEFAULT_PATH
	)

INCLUDE_DIRECTORIES(${CMAKE_CURRENT_SOURCE_DIR}/include)
INCLUDE_DIRECTORIES(${CMAKE_CURRENT_SOURCE_DIR})

if(WIN32)
	INCLUDE_DIRECTORIES("${BOOST_INCLUDE_DIRECTORIES}")
	if(CMAKE_CL_64)
		LINK_DIRECTORIES("${BOOST_INCLUDE_DIRECTORIES}/lib64")
	else(CMAKE_CL_64)
		LINK_DIRECTORIES("${BOOST_INCLUDE_DIRECTORIES}/lib")
	endif(CMAKE_CL_64)
	
    	ADD_DEFINITIONS("/DUNICODE /D_UNICODE")
endif(WIN32)

INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/pcre-7.4")

ADD_LIBRARY(mongoclient STATIC
	# single source file 
	${CMAKE_CURRENT_SOURCE_DIR}/client/mongo_client_lib.cpp
	)

if(WIN32)
    TARGET_LINK_LIBRARIES(mongoclient
      ws2_32.lib
      psapi.lib
      )
endif(WIN32)

