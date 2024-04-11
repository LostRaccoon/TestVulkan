# CMakeList.txt : Top-level CMake project file, do global configuration
# and include sub-projects here.
#
cmake_minimum_required (VERSION 3.8)

# Enable Hot Reload for MSVC compilers if supported.
if (POLICY CMP0141)
  cmake_policy(SET CMP0141 NEW)
  set(CMAKE_MSVC_DEBUG_INFORMATION_FORMAT "$<IF:$<AND:$<C_COMPILER_ID:MSVC>,$<CXX_COMPILER_ID:MSVC>>,$<$<CONFIG:Debug,RelWithDebInfo>:EditAndContinue>,$<$<CONFIG:Debug,RelWithDebInfo>:ProgramDatabase>>")
endif()

project ("TestCMake")

set(CMAKE_AUTORCC ON)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set_property(GLOBAL PROPERTY USE_FOLDERS ON)

find_package(Vulkan REQUIRED)
if (Vulkan_FOUND)
    message(STATUS "Vulkan found.")
    # 在这里添加你的项目设置
else()
    message(FATAL_ERROR "Vulkan not found.")
endif()

include_directories("C:/VulkanSDK/GLFW/include")  
link_directories("C:/VulkanSDK/GLFW/lib-vc2022")

include_directories("C:/VulkanSDK/GLM")  
include_directories("C:/VulkanSDK/1.3.280.0/Include")
# Include sub-projects.

add_subdirectory ("Ex00-VulkanWindow")