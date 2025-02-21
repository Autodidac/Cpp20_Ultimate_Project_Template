# Add executable
add_executable(Application1
   Application1.cpp
)

# Link StaticLib1
target_link_libraries(Application1 PRIVATE
    StaticLib1
)
# Specify include directories for Application1
target_include_directories(Application1 PRIVATE ${CMAKE_CURRENT_SOURCE_DIR})

# Use shared vcpkg installation directories
target_include_directories(Application1 PRIVATE
    ${VCPKG_INSTALLATION_ROOT}/x64-linux/include
)
target_link_directories(Application1 PRIVATE
    ${VCPKG_INSTALLATION_ROOT}/x64-linux/lib
)

# If you're targeting X11, make sure that the X11-specific source is added conditionally
if(UNIX AND NOT APPLE)  # Assuming this targets Linux/X11
   # target_sources(Static PRIVATE ../../src/Linux.cpp)
endif()

# Additional linker options for GNU/Clang
if(CMAKE_CXX_COMPILER_ID MATCHES "GNU|Clang")
    target_link_options(StaticLib1 PRIVATE -Wl,--allow-shlib-undefined)
endif()

# Installation rule for the executable
install(TARGETS Application1
    RUNTIME DESTINATION bin
)
