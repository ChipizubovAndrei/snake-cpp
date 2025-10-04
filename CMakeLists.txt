cmake_minimum_required(VERSION 3.24)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(CXX_FLAGS "-Wall")

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/bin)
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/bin)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/bin)

project(snake)

find_package(SDL2 REQUIRED)

set(SNAKE_SOURCES 
    src/main.cpp
    
    src/game.cpp
    src/game.h
    
    src/controller.cpp 
    src/controller.h 
    
    src/renderer.cpp 
    src/renderer.h 
    
    src/snake.cpp
    src/snake.h
)

add_executable(${PROJECT_NAME} ${SNAKE_SOURCES})

target_include_directories(${PROJECT_NAME} PRIVATE ./src)
target_link_libraries(${PROJECT_NAME} PRIVATE SDL2::SDL2main)
