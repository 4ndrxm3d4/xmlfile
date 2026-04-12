cmake_minimum_required(VERSION 3.10)
project(xmlfile VERSION 1.0.0 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Source files
set(SOURCES 
    main.cpp
    pugixml.cpp
)

# Executable
add_executable(xmlfile ${SOURCES})

# Target properties
target_include_directories(xmlfile PRIVATE ${CMAKE_CURRENT_SOURCE_DIR})

# Install rules
install(TARGETS xmlfile DESTINATION bin)
