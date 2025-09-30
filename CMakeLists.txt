cmake_minimum_required(VERSION 3.16...3.28)

# Set default app name if not provided
if(NOT DEFINED TORQUE_APP_NAME OR "${TORQUE_APP_NAME}" STREQUAL "")
    set(TORQUE_APP_NAME "3DAAK" CACHE STRING "Default app name")
endif()

# Set install path
set(CMAKE_INSTALL_PREFIX "${CMAKE_BINARY_DIR}/temp" CACHE PATH "default install path" FORCE)

# Define project
project(${TORQUE_APP_NAME})

# Include Torque build system
add_subdirectory(Tools/CMake)

# ✅ Add game project directory
add_subdirectory("My Projects/3DAAK")
