project(MagicBuild)
cmake_minimum_required(VERSION 3.0)

execute_process(COMMAND git rev-parse HEAD
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}
    OUTPUT_VARIABLE COMMIT_ID
    OUTPUT_STRIP_TRAILING_WHITESPACE
)

file(GLOB HOOK_SCRIPTS MagicBuildRepo/*)
if (HOOK_SCRIPTS)
    file(COPY ${HOOK_SCRIPTS} DESTINATION ${CMAKE_SOURCE_DIR}/../.git/hooks) 
endif (HOOK_SCRIPTS)



#if( CMAKE_RUNTIME_OUTPUT_DIRECTORY )
#	set( executableOutputPath ${CMAKE_RUNTIME_OUTPUT_DIRECTORY} )
#elseif( EXECUTABLE_OUTPUT_PATH )
#	set( executableOutputPath ${EXECUTABLE_OUTPUT_PATH} )
#else()
#	set( executableOutputPath ${CMAKE_CURRENT_BINARY_DIR} )
#endif()

set(ARCHIVE_OUTPUT_DIRECTORY  "/D:/BinariesDataFromMagicBuild/lib"
LIBRARY_OUTPUT_DIRECTORY  "/D:/BinariesDataFromMagicBuild/lib"
RUNTIME_OUTPUT_DIRECTORY  "/D:/BinariesDataFromMagicBuild/bin")


add_executable(magic_build main.cpp)
