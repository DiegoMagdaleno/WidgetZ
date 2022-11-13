cmake_minimum_required(VERSION 3.24)
project(WIDGETZ C)

set(CMAKE_C_STANDARD 11)
set(VCPKG_FEATURE_FLAGS "registries")

find_package(unofficial-allegro5 REQUIRED)
find_package(Freetype REQUIRED)

add_subdirectory(src)

include_directories(
	${WIDGETZ_SOURCE_DIR}/include
)