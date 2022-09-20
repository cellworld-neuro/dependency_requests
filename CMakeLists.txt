cmake_minimum_required(VERSION 3.10)

set(CMAKE_CXX_STANDARD 20)

project(project
        VERSION 2022.0.0
        DESCRIPTION "easy http requests library"
        LANGUAGES CXX)

find_package(CURL)

set (requests_files
        src/request.cpp
        src/response.cpp
        )

add_library(requests ${requests_files})


SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -pthread -fPIC")

include_directories(include)

target_link_libraries(requests
        PUBLIC
        ${CURL_LIBRARIES})