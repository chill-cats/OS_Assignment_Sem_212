cmake_minimum_required(VERSION 3.15)

project(OS_Lab C)

add_library(project_settings INTERFACE)
target_compile_features(project_settings INTERFACE c_std_11)

find_package(Threads REQUIRED)

add_subdirectory(src/common out/common)
add_subdirectory(src/os out/os)
add_subdirectory(src/cpu out/cpu)
add_subdirectory(src/mem out/mem)
add_subdirectory(src/timer out/timer)
add_subdirectory(src/loader out/loader)
add_subdirectory(src/sched out/sched)
add_subdirectory(src/queue out/queue)

add_subdirectory(src/paging out/paging)

add_custom_target(Test_mem_0 ALL paging m0 
                DEPENDS paging 
                COMMENT "------ MEMORY MANAGEMENT TEST 0 ------------------------------------" 
                WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/input/proc)

add_custom_target(Test_mem_1 ALL paging m1 
                DEPENDS paging 
                COMMENT "------ MEMORY MANAGEMENT TEST 1 ------------------------------------" 
                WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/input/proc)

add_custom_target(Test_sched_1 ALL os sched_0
                DEPENDS os 
                COMMENT "------ SCHEDULING TEST 0 -------------------------------------------" 
                WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})

add_custom_target(Test_sched_2 ALL os sched_1
                DEPENDS os 
                COMMENT "------ SCHEDULING TEST 1 -------------------------------------------" 
                WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})
                
add_custom_target(Test_os_0 ALL os os_0
                DEPENDS os 
                COMMENT "------ OS TEST 0 ---------------------------------------------------" 
                WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})

add_custom_target(Test_os_1 ALL os os_1
                DEPENDS os 
                COMMENT "------ OS TEST 1 ---------------------------------------------------" 
                WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})