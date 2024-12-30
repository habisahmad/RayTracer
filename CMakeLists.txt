cmake_minimum_required(VERSION 3.13) 
project(RayTracer)                  
set(CMAKE_CXX_STANDARD 14)          # Use C++14 standard

# Add source files
set(SOURCE_FILES
    src/main.cc
)

add_executable(RayTracer ${SOURCE_FILES})

if(MSVC) 
    set(CMAKE_RUNTIME_OUTPUT_DIRECTORY_DEBUG "${CMAKE_BINARY_DIR}/Debug")
    set(CMAKE_RUNTIME_OUTPUT_DIRECTORY_RELEASE "${CMAKE_BINARY_DIR}/Release")
else()
    set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}")
endif()