add_library(mem mem.c mem.h)
target_include_directories(mem PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
target_link_libraries(mem PRIVATE project_settings common)