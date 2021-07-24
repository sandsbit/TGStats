cmake_minimum_required(VERSION 3.8)
project(tgtools VERSION 1.0 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 20)

include(../../cmake/compiler-options.cmake)

aux_source_directory(. tgtools_sources)

add_library(tgtools SHARED ${tgtools_sources})
target_compile_definitions(tgtools PRIVATE BUILDING_DLL)
target_include_directories(tgtools PUBLIC .)

set_target_properties(tgtools PROPERTIES
        CXX_STANDARD 20
        CXX_STANDARD_REQUIRED YES)

add_library(TGStats::TGTools ALIAS tgtools)