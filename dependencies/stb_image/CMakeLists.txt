add_library(stb_image "${CMAKE_CURRENT_LIST_DIR}/src/stb_image.cpp")
target_include_directories(stb_image PUBLIC ${CMAKE_CURRENT_LIST_DIR}/include)