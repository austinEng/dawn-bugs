cmake_minimum_required(VERSION 3.0...3.28)

project(DawnRepro LANGUAGES CXX C)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)  # clangd

add_subdirectory(third_party)

add_executable(App src/main.cpp)
target_include_directories(App PRIVATE ${PROJECT_SOURCE_DIR}/src)
target_include_directories(App PRIVATE ${PROJECT_SOURCE_DIR}/third_party/dawn/include)
target_link_libraries(App
  dawn_proc
  webgpu_dawn
  webgpu_cpp
  webgpu_glfw
  glfw
)
