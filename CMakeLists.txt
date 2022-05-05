cmake_minimum_required(VERSION 3.10)
project(GeminiGraph)

set(MPI_C_COMPILER "/home/sunsx/opt/openmpi/bin/mpicc")
set(MPI_CXX_COMPILER "/home/sunsx/opt/openmpi/bin/mpicxx")

set(CMAKE_CXX_FLAGS
        "${CMAKE_CXX_FLAGS} -std=c++14 -O2 -Wall -fopenmp -march=native")

find_package(MPI REQUIRED)
if (MPI_FOUND)
    include_directories(SYSTEM ${MPI_INCLUDE_PATH})
else (MPI_FOUND)
    message(SEND_ERROR "This application cannot compile without MPI")
endif (MPI_FOUND)

include_directories(${PROJECT_SOURCE_DIR})
add_subdirectory(toolkits)

add_executable(converter.out convert_to_gemini_format.cpp)
