cmake_minimum_required(VERSION 2.8.4)

# Check the dependencies here

INCLUDE_DIRECTORIES(${CMAKE_CURRENT_SOURCE_DIR}/include)
INCLUDE_DIRECTORIES(${CMAKE_CURRENT_SOURCE_DIR})

message(${CMAKE_CURRENT_SOURCE_DIR})

ADD_LIBRARY(mongoclient STATIC
	# single source file 
	client/mongo_client_lib.cpp
	)

TARGET_LINK_LIBRARIES(mongo_lib
	# boost and pcre
	)

