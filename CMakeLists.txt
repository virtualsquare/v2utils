cmake_minimum_required(VERSION 3.7)
project("v2utils")

set(PROJECT_INCLUDEDIR ${CMAKE_BINARY_DIR}/include)
execute_process(COMMAND mkdir -p ${PROJECT_INCLUDEDIR})

add_subdirectory(strcase)
add_subdirectory(libstropt)
add_subdirectory(libfduserdata)
add_subdirectory(libvpoll-eventfd)
add_subdirectory(libvolatilestream)
add_subdirectory(userbindmount)
