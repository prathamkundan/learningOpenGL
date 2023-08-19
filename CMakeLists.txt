cmake_minimum_required(VERSION 3.10)

project(oglProj VERSION 0.0)

find_package(OpenGL REQUIRED)

add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/dependencies/glad)
add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/dependencies/stb_image)
add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/dependencies/glm)
include(${CMAKE_CURRENT_SOURCE_DIR}/dependencies/glfw/CMakeLists.txt)

file(GLOB_RECURSE src_files ${CMAKE_CURRENT_SOURCE_DIR}/src/*.[ch]pp)
file(GLOB_RECURSE include_files ${CMAKE_CURRENT_SOURCE_DIR}/include/*.[ch]pp)

message(INFO ${src_files})

add_executable(main "${src_files}")

target_link_libraries(main PUBLIC glad stb_image glm ${GLFW_LIBRARIES})
target_include_directories(
    main PUBLIC  
    ${GLFW_INCLUDE_DIR} 
    ${CMAKE_CURRENT_SOURCE_DIR}/include/shaders
)