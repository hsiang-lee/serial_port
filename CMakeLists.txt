
cmake_minimum_required(VERSION 3.20)

project(serial_port)
    
set(Sources src/serial.cc)

#linux by default
list(APPEND Sources src/impl/unix.cc)
list(APPEND Sources src/impl/list_ports/list_ports_linux.cc)

add_compile_options(-std=c++17)
add_library(serial_port ${Sources})
target_include_directories(serial_port PUBLIC include src)

install(TARGETS ${PROJECT_NAME} DESTINATION ${RELEASE_PATH})
