cmake_minimum_required(VERSION 2.8.6)

project(hola)

enable_testing()

#Boost unit test framework
find_package(Boost REQUIRED)

include_directories(
	${Boost_INCLUDE_DIRS}
)

set (SOURCES
	src/hola.cpp
)

set (HEADERS
	src/hola.hpp
)

add_executable(test_hola test/test_hola.cpp)


add_executable(hola ${SOURCES} ${HEADERS})

target_link_libraries(test_hola  ${BOOST_INCLUDE_DIRS})
