cmake_minimum_required(VERSION 3.31)

# set the project name and version
project(Storage VERSION 1.0)

file(GLOB_RECURSE ALL_CC_FILES *.cc)
file(GLOB_RECURSE ALL_H_FILES *.h)
# 创建一个列表，用于存储排除test.cc后的文件列表
set(CC_FILES_WITHOUT_TEST)

# 遍历找到的所有.cc文件，排除test.cc
foreach(CC_FILE ${ALL_CC_FILES})
    if(NOT "${CC_FILE}" STREQUAL "${CMAKE_CURRENT_SOURCE_DIR}/src/test.cc")
        list(APPEND CC_FILES_WITHOUT_TEST ${CC_FILE})
    endif()
endforeach()

message("${CC_FILES_WITHOUT_TEST}")
message("${ALL_H_FILES}")

add_library(storage_lib ${ALL_CC_FILES} ${ALL_H_FILES})
# 添加可执行文件，使用排除test.cc后的文件列表作为源文件
add_executable(my_project ${CC_FILES_WITHOUT_TEST})