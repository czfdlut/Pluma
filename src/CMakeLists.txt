project(Pluma)
set(LIBRARY_OUTPUT_PATH ${Pluma_SOURCE_DIR}/../output/libPluma/lib)

add_definitions(-g -D _LIB -D _LINUX64)

include_directories(
./
./Pluma
../include
../include/Pluma
)

file(GLOB ALL_HEADER_SRCS
./Pluma/*.h
./Pluma/*.hpp
../include/Pluma/*.h
../include/Pluma/*.hpp
../include/Pluma/*.inl
)
file(GLOB ALL_CXX_SRCS
./Pluma/*.cpp
)

set(ALL_LIB pthread dl)
add_library(Pluma STATIC ${ALL_HEADER_SRCS} ${ALL_CXX_SRCS})
target_link_libraries(Pluma ${ALL_LIB})
