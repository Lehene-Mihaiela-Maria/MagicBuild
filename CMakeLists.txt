project(MagicBuild)
cmake_minimum_required(VERSION 3.0)

#salvez partea build-ul in alt director numit bin
SET(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${SaveBinanry_SOURCE_DIR}/bin)

add_executable(magic_build main.cpp)
