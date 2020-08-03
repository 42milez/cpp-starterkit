add_executable(cppsk main.cc)
add_subdirectory(core)
target_link_libraries(cppsk core)
