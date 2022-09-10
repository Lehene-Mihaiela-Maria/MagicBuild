project(MagicBuild)
cmake_minimum_required(VERSION 3.0)

file(GLOB HOOK_SCRIPTS MagicBuildRepo/*)
if (HOOK_SCRIPTS)
    file(COPY ${"D:\\MagicBuildRepo\\.git\\hooks"} DESTINATION ${"D:\\MagicBuildRepo\\build\\magic_build.dir"}/../.git/hooks) 
endif (HOOK_SCRIPTS)

add_executable(magic_build main.cpp)
