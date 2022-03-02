add_library(queue queue.c queue.h)
target_include_directories(queue PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
target_link_libraries(queue PRIVATE project_settings common scheduler)