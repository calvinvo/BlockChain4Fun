cmake_minimum_required(VERSION 3.0.0 FATAL_ERROR)
##################################################
file(
	GLOB 
		CORE_SRC
			src/*.cpp
	)
file(
	GLOB
		CORE_INCLUDE
			include/*.h
			include/*.hpp
	)
	
add_library(
	libblc_core
		STATIC
		${CORE_SRC}
		${CORE_INCLUDE}
	)

include_directories(
	libblc_core
		PRIVATE
			include
			#add dependencies 
			${CURL_LIB_DIR}/include
			${SSL_LIB_DIR}/include
	)

target_link_libraries(
	libblc_core
		libcurl.lib
		libcurl.dll.lib #why dll here ?
		libeay32.lib
		ssleay32.lib
	)

	

			

	
