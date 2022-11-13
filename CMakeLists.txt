cmake_minimum_required(VERSION 3.24)
project(WIDGETZ C)

set(CMAKE_C_STANDARD 11)
set(VCPKG_FEATURE_FLAGS "registries")

include(FindPkgConfig)
set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${CMAKE_SOURCE_DIR}/CMake/Modules")
find_package(Allegro REQUIRED)
find_package(Freetype REQUIRED)

add_subdirectory(src)

include_directories(
	${WIDGETZ_SOURCE_DIR}/include
)