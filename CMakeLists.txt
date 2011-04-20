cmake_minimum_required(VERSION 2.8.4)

# Check the dependencies here
## Find mongo includes
#
#find_path(MONGO_INCLUDE_DIRECTORIES
#	NAMES client/dbclient.h
#	PATHS
#		/home/dhan/src/mongo
#		c:/Dhan/git/mongo
#		NO_DEFAULT_PATH
#)
#
##Find boost libraries
#find_path(BOOST_INCLUDE_DIRECTORIES
#NAMES boost/any.hpp
#		PATHS
#				/usr/local/include/mongo
#				/usr/include/mongo
#				/usr/include
#				c:/boost
#				c:/Dhan/git/mongo
#				NO_DEFAULT_PATH
#	)
#  
#  INCLUDE_DIRECTORIES(${BOOST_INCLUDE_DIRECTORIES})

INCLUDE_DIRECTORIES(${CMAKE_CURRENT_SOURCE_DIR}/include)
INCLUDE_DIRECTORIES(${CMAKE_CURRENT_SOURCE_DIR})

message(${CMAKE_CURRENT_SOURCE_DIR})

ADD_LIBRARY(mongo_lib STATIC
	# single source file 
	client/mongo_client_lib.cpp
	)

TARGET_LINK_LIBRARIES(mongo_lib
	# boost and pcre
	)

