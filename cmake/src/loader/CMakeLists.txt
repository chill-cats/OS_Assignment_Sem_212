add_library(loader loader.c loader.h)
target_include_directories(loader PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
target_link_libraries(loader PRIVATE project_settings common)