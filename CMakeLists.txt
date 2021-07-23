cmake_minimum_required(VERSION 3.19)
project(TGStats VERSION 1.0 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 20)

find_package(nlohmann_json 3.9.1 REQUIRED)

add_executable(TGStats tgstats/main.cpp)
target_link_libraries(TGStats PRIVATE nlohmann_json::nlohmann_json)