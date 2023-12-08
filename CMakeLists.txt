cmake_minimum_required(VERSION 3.12)

# Project Name
set(PROJECT_NAME "DeepX" CACHE STRING "Project Name")

project(${PROJECT_NAME})

# C++ Standard
set(CMAKE_CXX_STANDARD 20 CACHE STRING "C++ Standard")
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Source Directory
set(SOURCE_DIR "${CMAKE_SOURCE_DIR}/src" CACHE PATH "Source Directory")

# Include Directory
set(INCLUDE_DIR "${CMAKE_SOURCE_DIR}/include" CACHE PATH "Include Directory")

# Add source files
file(GLOB_RECURSE SOURCE_FILES "${SOURCE_DIR}/*.cpp")

# Add header files
file(GLOB_RECURSE HEADER_FILES "${INCLUDE_DIR}/*.h")

# Add executable target
add_executable(${PROJECT_NAME} ${SOURCE_FILES} ${HEADER_FILES})

# Set include directories
target_include_directories(${PROJECT_NAME} PRIVATE ${INCLUDE_DIR})
