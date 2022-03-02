add_executable(os os.c)
target_link_libraries(os PRIVATE project_settings common cpu mem timer loader scheduler Threads::Threads)
set_target_properties(os PROPERTIES RUNTIME_OUTPUT_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/../../out)