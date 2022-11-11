cmake_minimum_required(VERSION 3.10)

add_library(imgui STATIC 
	imgui.cpp
	imgui_demo.cpp
	imgui_draw.cpp
	imgui_tables.cpp
	imgui_widgets.cpp
	backends/imgui_impl_glfw.cpp
    backends/imgui_impl_opengl3.cpp
	#backends/imgui_impl_vulkan.cpp
)

set(GLFW_SOURCE_DIR "../glfw")
set(GLFW_INCLUDE_DIR "${GLFW_SOURCE_DIR}/include")
set(GLAD_INCLUDE_DIR "../Glad/include")

# outside the lib root dir 
include_directories(${GLFW_INCLUDE_DIR})
include_directories(${GLAD_INCLUDE_DIR}) 

target_link_libraries(imgui PUBLIC glad glfw dl pthread)
target_include_directories(imgui PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}")


