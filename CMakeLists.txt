cmake_minimum_required(VERSION 3.7 FATAL_ERROR)

if(NOT DEFINED CMAKE_C_COMPILER)
set (CMAKE_C_COMPILER cl.exe)
endif()

project(lua LANGUAGES C)

add_library(lua STATIC "")

target_sources(lua
  PRIVATE
    lapi.c
    lauxlib.c
    lbaselib.c
    lcode.c
    lcorolib.c
    lctype.c
    ldblib.c
    ldebug.c
    ldo.c
    ldump.c
    lfunc.c
    lgc.c
    linit.c
    liolib.c
    llex.c
    lmathlib.c
    lmem.c
    loadlib.c
    lobject.c
    lopcodes.c
    loslib.c
    lparser.c
    lstate.c
    lstring.c
    lstrlib.c
    ltable.c
    ltablib.c
    #ltests.c
    ltm.c
    #lua.c
    lundump.c
    lutf8lib.c
    lvm.c
    lzio.c
    #onelua.c
)

target_include_directories(lua
  PUBLIC
    ${CMAKE_CURRENT_SOURCE_DIR}
)

#target_link_libraries(lua
#  PUBLIC
#    $)

add_executable(luac lua.c)

target_link_libraries(luac lua)
