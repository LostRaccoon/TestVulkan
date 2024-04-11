# CMakeList.txt : CMake project for Ex00-VulkanWindow, include source and define
# project specific logic here.
#

# Add source to this project's executable.
add_executable (Ex00-VulkanWindow main.cpp VulkanRenderer.cpp)

if (CMAKE_VERSION VERSION_GREATER 3.12)
  set_property(TARGET Ex00-VulkanWindow PROPERTY CXX_STANDARD 20)
endif()

# TODO: Add tests and install targets if needed.
#target_link_libraries(Ex00-VulkanWindow PRIVATE ${Vulkan_LIBRARIES})

target_link_libraries(Ex00-VulkanWindow PRIVATE ${Vulkan_LIBRARIES} C:/VulkanSDK/GLFW/lib-vc2022/glfw3.lib)
#target_link_libraries(Ex00-VulkanWindow PRIVATE C:/VulkanSDK/GLFW/lib-vc2022/glfw3_mt.lib)
#target_link_libraries(Ex00-VulkanWindow PRIVATE C:/VulkanSDK/GLFW/lib-vc2022/glfw3dll.lib)
#set (LIB_FFMPEG "glfw3.lib" "glfw3_mt.lib" "glfw3dll.lib")
#target_link_libraries(Ex00-VulkanWindow PRIVATE ${LIB_FFMPEG})