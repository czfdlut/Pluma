project(SimpleWarrior)
set(EXECUTABLE_OUTPUT_PATH ${SimpleWarrior_SOURCE_DIR}/../output/)

add_definitions(-g -D _LIB -D _LINUX64)

link_directories(${SimpleWarrior_SOURCE_DIR}/../../../output/libPluma/lib)

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
../interface/*.cpp
)

set(ALL_LIB Pluma pthread dl)
ADD_EXECUTABLE(SimpleWarrior ${ALL_HEADER_SRCS} ${ALL_CXX_SRCS})
target_link_libraries(SimpleWarrior ${ALL_LIB})
