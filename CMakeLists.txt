cmake_minimum_required(VERSION 3.17)

set_property(GLOBAL PROPERTY USE_FOLDERS ON)

project(Probulator)

if(MSVC)
	add_definitions(
		-D_CRT_SECURE_NO_WARNINGS
		-D_CRT_SECURE_NO_DEPRECATE
	)
	set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} /MP /Zo")
else()
	# suppress some common warnings from eigen
	add_definitions(
		-Wno-deprecated-declarations
		-Wno-ignored-attributes
	)
endif()

add_subdirectory(Source)
