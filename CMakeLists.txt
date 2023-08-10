cmake_minimum_required(VERSION 3.10)

find_package(OpenGL REQUIRED)

project (test_project)
include_directories("./include")
add_executable(main ${CMAKE_CURRENT_SOURCE_DIR}"/src/main.cpp" ${CMAKE_CURRENT_SOURCE_DIR}"/src/glad.c")

# target_link_directories(main PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}/lib/")
target_link_libraries(main ${CMAKE_CURRENT_SOURCE_DIR}/lib/libglfw3.a)