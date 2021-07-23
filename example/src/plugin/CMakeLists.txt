project(WarriorsPlugin)
set(LIBRARY_OUTPUT_PATH ${WarriorsPlugin_SOURCE_DIR}/../output/plugins)

add_definitions(-g -D _LIB -D _LINUX64)

include_directories(
../../../include
../../../include/Pluma
../interface
./
)

file(GLOB ALL_HEADER_SRCS
../../../include/Pluma/*.hpp
../../../include/Pluma/*.inl
../interface/*.hpp
./*.hpp
)

file(GLOB ALL_CXX_SRCS
./*.cpp
)

set(ALL_LIB pthread dl)
add_library(WarriorsPlugin SHARED ${ALL_HEADER_SRCS} ${ALL_CXX_SRCS})
target_link_libraries(WarriorsPlugin ${ALL_LIB})
