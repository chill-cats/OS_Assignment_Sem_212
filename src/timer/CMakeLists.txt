add_library(timer timer.c timer.h)
target_include_directories(timer PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
target_link_libraries(timer PRIVATE project_settings common)