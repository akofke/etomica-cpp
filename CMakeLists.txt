cmake_minimum_required(VERSION 3.13)
project(etomica-cpp)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

add_compile_definitions(SFMT_MEXP=19937 HAVE_SSE2)
add_compile_options()

include_directories(src)

file(GLOB ETOMICA_SOURCES src/*.cpp)

add_executable(md src/apps/main-md.cpp ${ETOMICA_SOURCES} )
add_executable(mc src/apps/main-mc.cpp ${ETOMICA_SOURCES} )
add_executable(dimer src/apps/main-dimer.cpp ${ETOMICA_SOURCES} )
add_executable(eam src/apps/main-eam.cpp ${ETOMICA_SOURCES} )
add_executable(eam-mc src/apps/main-eam-mc.cpp ${ETOMICA_SOURCES} )
add_executable(mix src/apps/main-mix.cpp ${ETOMICA_SOURCES} )
add_executable(virial src/apps/main-virial.cpp ${ETOMICA_SOURCES} )
add_executable(virial-overlap src/apps/main-virial-overlap.cpp ${ETOMICA_SOURCES} )
add_executable(water-mc src/apps/main-water-mc.cpp ${ETOMICA_SOURCES} )
#set_target_properties(md PROPERTIES INTERPROCEDURAL_OPTIMIZATION true)