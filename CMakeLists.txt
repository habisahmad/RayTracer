cmake_minimum_required(VERSION 3.13) # Minimum required CMake version
project(RayTracer)                  # Project name
set(CMAKE_CXX_STANDARD 14)          # Use C++14 standard

# Add source files
set(SOURCE_FILES
    main.cc
    ray.h
    vec3.h
    color.h
)

# Add executable target
add_executable(RayTracer ${SOURCE_FILES})

# Add debug and release configuration settings
if(MSVC) # If using Microsoft Visual Studio
    set(CMAKE_RUNTIME_OUTPUT_DIRECTORY_DEBUG "${CMAKE_BINARY_DIR}/Debug")
    set(CMAKE_RUNTIME_OUTPUT_DIRECTORY_RELEASE "${CMAKE_BINARY_DIR}/Release")
else()
    set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}")
endif()

# Optional: Add custom build type (if needed)
if(NOT CMAKE_BUILD_TYPE)
    set(CMAKE_BUILD_TYPE Release)
endif()

# Optional: Add include directories (if headers aren't in the root directory)
# target_include_directories(RayTracer PUBLIC ${CMAKE_SOURCE_DIR}/include)
