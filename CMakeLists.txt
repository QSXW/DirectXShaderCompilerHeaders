cmake_minimum_required(VERSION 3.16)

project("DirectXShaderCompilerHeaders" LANGUAGES CXX)

add_library(${PROJECT_NAME} INTERFACE)

target_include_directories(${PROJECT_NAME} INTERFACE "${CMAKE_CURRENT_SOURCE_DIR}/dxc/inc")

if (${CMAKE_CXX_COMPILER_ID} MATCHES "Clang$")
    target_compile_options(${PROJECT_NAME} INTERFACE -fms-extensions)
endif()
