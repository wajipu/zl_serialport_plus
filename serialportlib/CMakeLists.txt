cmake_minimum_required(VERSION 3.4.1)

# 导出文件路径
# set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/src/main/jniLibs/${ANDROID_ABI})
# 创建共享库 serial-port
add_library(
    serial-port
    SHARED
    src/main/cpp/serial-port.cpp
)
# 查找日志库
find_library(
    log-lib
    log
)

# 链接日志库以及 C++ 标准库（如需要）
target_link_libraries(
    serial-port
    ${log-lib}
    c++_shared  # 或 c++_static
)



# 可选调试信息
message(STATUS "Building serial-port library from: src/main/cpp/serial-port.cpp")
