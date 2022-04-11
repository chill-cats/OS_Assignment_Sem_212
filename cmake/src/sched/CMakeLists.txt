add_library(scheduler sched.c sched.h)
target_include_directories(scheduler PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
target_link_libraries(scheduler PRIVATE project_settings common queue)