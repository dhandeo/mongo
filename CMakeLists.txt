cmake_minimum_required(VERSION 2.8.4)

# Check the dependencies here

ADD_LIBRARY(mongo_lib STATIC
	# single source file 
	client/mongo_client_lib.cpp
	)

TARGET_LINK_LIBRARIES(mongo_lib
	# boost and pcre
	)

