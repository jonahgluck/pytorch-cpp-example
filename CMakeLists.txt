cmake_minimum_required(VERSION 3.18)

project(apresearch VERSION 1.0.0 LANGUAGES CXX)

set(CMAKE_PREFIX_PATH /home/jonahgluck/Downloads/libtorch)

set(CUDNN_INCLUDE_DIR /usr/local/cuda/include)
set(CUDNN_INCLUDE_PATH /usr/local/cuda/include)
set(CUDNN_LIB_DIR /usr/local/cuda/lib64)
set(CUDNN_PATH /usr/local/cuda/lib64/libcudnn.so.7)
set(CUDNN_LIBRARY_PATH /usr/local/cuda/lib64)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} ${TORCH_CXX_FLAGS}")

set(EXECUTABLE_NAME apresearch)

find_package(Torch REQUIRED)

add_executable(${EXECUTABLE_NAME})

target_sources(${EXECUTABLE_NAME} PRIVATE src/main.cpp)

# target_include_directories(${EXECUTABLE_NAME} PRIVATE include)

target_link_libraries(${EXECUTABLE_NAME} ${TORCH_LIBRARIES})

set_property(TARGET ${PROJECT_NAME} PROPERTY CXX_STANDARD 14)

