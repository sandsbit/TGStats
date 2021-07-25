cmake_minimum_required(VERSION 3.8)
project(TGStats VERSION 1.0 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 20)

include(../cmake/compiler-options.cmake)

add_subdirectory(tgtools)

find_package(spdlog REQUIRED)

aux_source_directory(. core_sources)

add_executable(TGStats ${core_sources})
target_include_directories(TGStats PUBLIC .)

target_link_libraries(TGStats PUBLIC TGStats::TGTools)
target_link_libraries(TGStats PRIVATE spdlog::spdlog)

set_target_properties(TGStats PROPERTIES
        CXX_STANDARD 20
        CXX_STANDARD_REQUIRED YES)