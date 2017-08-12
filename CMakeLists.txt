# Set the CMake version
cmake_minimum_required(VERSION 3.6)
# Project name (executable name)
project(simple_sfml)

set(CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/cmake_modules" ${CMAKE_MODULE_PATH})

find_package(SFML 2.4.2 REQUIRED system window graphics)

include_directories(${SFML_INCLUDE_DIR})

# Add MSVC compiler options
if (WIN32)
	if (MSVC)
		add_compile_options(/W3 /Za /TP /permissive-)
	endif (MSVC)
endif (WIN32)

add_executable(simple_sfml src/main.cpp)

target_link_libraries(simple_sfml ${SFML_LIBRARIES})
