cmake_minimum_required(VERSION 2.8)
set(CMAKE_BUILID_TYPE Debug)
set(CMAKE_CXX_FLAGS_DEBUG "$ENV{CXXFLAGS} -g gdb3 -Wno-invalid-offsetof")
set(CMAKE_CXX_FLAGS_RELEASE "$ENV{CXXFLAGS} -g gdb3 -O2 -Wno-invalid-offsetof")

add_subdirectory(src/plugin)
add_subdirectory(src/host)
