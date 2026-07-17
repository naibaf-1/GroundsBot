cmake_minimum_required(VERSION 3.20)
project(grounds_bot_control)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# Find dependencies
find_package(ament_cmake REQUIRED)
find_package(rclcpp REQUIRED)

# Add an exectuable:
add_executable(wheel_controller_node src/wheel_controller_node.cpp)
# Link all dependencies for the executable
ament_target_dependencies(wheel_controller_node rclcpp)

install (TARGETS
	# Install the executable
  wheel_controller_node
	DESTINATION lib/${PROJECT_NAME}/
)

ament_package()
