# CMakeList.txt : Top-level CMake project file, do global configuration
# and include sub-projects here.
#
cmake_minimum_required (VERSION 3.8)

project(cmakeapp1 VERSION 1.0
                  DESCRIPTION "My Project Description"
                  LANGUAGES CXX)

# Set C++ standard
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

# Enable Hot Reload for MSVC compilers if supported
if (POLICY CMP0141)
    cmake_policy(SET CMP0141 NEW)
    set(CMAKE_MSVC_DEBUG_INFORMATION_FORMAT "$<IF:$<AND:$<C_COMPILER_ID:MSVC>,$<CXX_COMPILER_ID:MSVC>>,$<$<CONFIG:Debug,RelWithDebInfo>:EditAndContinue>,$<$<CONFIG:Debug,RelWithDebInfo>:ProgramDatabase>>")
endif()

# Enforce install location at top-level (in the project root)
set(CMAKE_INSTALL_PREFIX "${CMAKE_SOURCE_DIR}/built" CACHE PATH "Install path prefix" FORCE)
message(STATUS "Install Prefix: ${CMAKE_INSTALL_PREFIX}")


# Configure vcpkg installation root
if(DEFINED ENV{VCPKG_INSTALLATION_ROOT})
    set(VCPKG_INSTALLATION_ROOT "$ENV{VCPKG_INSTALLATION_ROOT}/vcpkg_installed")
else()
    set(VCPKG_INSTALLATION_ROOT "${CMAKE_SOURCE_DIR}/vcpkg_installed")
endif()

# Include sub-projects
add_subdirectory("cmakeapp1")
add_subdirectory("app1")

#add_subdirectory ("Application1")
#add_subdirectory ("StaticLib1")

















