cmake_minimum_required(VERSION 3.22)
project(minimal_example_consumer)

set(CMAKE_CXX_STANDARD 20)

find_package(minimal_example CONFIGS REQUIRED)

add_executable(minimal_example_consumer main.cpp)

target_link_libraries(minimal_example_consumer minimal_example::b)

target_include_directories(minimal_example_consumer PUBLIC ${minimal_example_INCLUDE_DIR})

# Without line below fmt headers will not be found
#target_include_directories(minimal_example_consumer PUBLIC ${fmt_INCLUDE_DIR})

MESSAGE(WARNING ${CMAKE_INCLUDE_PATH})