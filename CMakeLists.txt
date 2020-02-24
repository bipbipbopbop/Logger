### Configuration ###
cmake_minimum_required(VERSION 3.0.0)

project(Logger VERSION 1.0.0)

# C++ Compilation specs
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

### Main Target ###
add_library(${PROJECT_NAME} INTERFACE)
set(SRC_DIR "source/")

# source files
set(INC
    Logger.hpp
)

list(TRANSFORM INC PREPEND ${CMAKE_CURRENT_SOURCE_DIR}/${SRC_DIR})

# add target dependencies
target_sources(${PROJECT_NAME} INTERFACE ${INC})
target_include_directories(${PROJECT_NAME} INTERFACE
                           ${SRC_DIR}
)
