project(MagicBuild)
cmake_minimum_required(VERSION 3.0)

exec_program(
  "git"
  ${CMAKE_CURRENT_SOURCE_DIR}
  ARGS "describe"
  OUTPUT_VARIABLE GIT_TAG )

#...if not found get the SHA1 hash instead
if( ${GIT_TAG} MATCHES "fatal:.*" )
exec_program(
  "git"
  ${CMAKE_CURRENT_SOURCE_DIR}
  ARGS "rev-parse HEAD"
  OUTPUT_VARIABLE GIT_VERSION )
else()
  set( GIT_VERSION ${GIT_TAG} )
endif()
add_definitions( -DAPP_GIT_VERSION="${GIT_VERSION}")

SET(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${SaveBinanry_SOURCE_DIR}/directory_bin)


add_executable(magic_build main.cpp)
