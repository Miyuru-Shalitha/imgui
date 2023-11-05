cmake_minimum_required(VERSION 3.26)

project("imgui")

file(GLOB SOURCE_FILES "${CMAKE_CURRENT_SOURCE_DIR}/*.cpp")

add_library(
    ${PROJECT_NAME} STATIC
    ${SOURCE_FILES}
    "${CMAKE_CURRENT_SOURCE_DIR}/backends/imgui_impl_opengl3.cpp"
    "${CMAKE_CURRENT_SOURCE_DIR}/backends/imgui_impl_glfw.cpp"
)

target_include_directories(
    ${PROJECT_NAME}
    PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}"
    PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}/backends"
    PRIVATE "${CMAKE_CURRENT_SOURCE_DIR}/../glfw/include"
)
