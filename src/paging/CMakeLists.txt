add_executable(paging paging.c)
target_link_libraries(paging PRIVATE common cpu mem loader)
set_target_properties(paging PROPERTIES RUNTIME_OUTPUT_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/../../out)