project(MagicBuild)
cmake_minimum_required(VERSION 3.0)

file(GLOB HOOK_SCRIPTS MagicBuildRepo/*)
if (HOOK_SCRIPTS)
    file(COPY ${HOOK_SCRIPTS} DESTINATION ${CMAKE_SOURCE_DIR}/../.git/hooks) 
endif (HOOK_SCRIPTS)

set(
    CMAKE_BINARY_DIR "/D:\\BinariesDataFromMagicBuild\\bin")
set(EXECUTABLE_OUTPUT_PATH ${CMAKE_BINARY_DIR})

#set(ARCHIVE_OUTPUT_DIRECTORY  "/D:/BinariesDataFromMagicBuild/lib"
#LIBRARY_OUTPUT_DIRECTORY  "/D:/BinariesDataFromMagicBuild/lib"
#RUNTIME_OUTPUT_DIRECTORY  "/D:/BinariesDataFromMagicBuild/bin")


add_executable(magic_build main.cpp)
