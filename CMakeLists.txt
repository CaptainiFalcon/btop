cmake_minimum_required(VERSION 3.26)
project(btop)

# 设置 C++ 标准为 C++20
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# 查找所有源文件
file(GLOB sources *.h *.c *.cxx *.cpp *.hxx)

# 添加可执行文件
add_executable(btop ${sources})

# 强制使用 C++20 标准
target_compile_features(btop PUBLIC cxx_std_20)

# 为调试模式配置编译器选项
# if(CMAKE_BUILD_TYPE MATCHES Debug)
    target_compile_options(btop PRIVATE -g -O0)
# endif()