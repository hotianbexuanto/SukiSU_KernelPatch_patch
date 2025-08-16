cmake_minimum_required(VERSION 3.22)
project(patch_project)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# 检测构建类型
if(ANDROID)
    set(TARGET_NAME "patch_android")
else()
    set(TARGET_NAME "patch")
endif()

# 编译主程序
add_executable(${TARGET_NAME} main.cpp)

# 包含目录 - 头文件应该已经在CI中预先生成
target_include_directories(${TARGET_NAME} PRIVATE 
    ${CMAKE_CURRENT_SOURCE_DIR}/include
    ${CMAKE_CURRENT_SOURCE_DIR}
)

# 链接配置
if(NOT ANDROID)
    target_link_libraries(${TARGET_NAME} PRIVATE -static)
endif()