add_executable(rudp main.cc)
add_subdirectory(core)
target_link_libraries(rudp core)
