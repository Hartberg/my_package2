cmake_minimum_required(VERSION 3.8)
project(my_package2)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)
#find_package(gz-sim REQUIRED)
#find_package(gz-msgs REQUIRED)
#find_package(gz-transport REQUIRED)

#lidar
#add_executable(lidar_node src/lidar_node.cpp)
#ament_target_dependencies(lidar_node rclcpp gz-msgs gz-transport)

# uncomment the following section in order to fill in
# further dependencies manually.
# find_package(<dependency> REQUIRED)

if(BUILD_TESTING)
  find_package(ament_lint_auto REQUIRED)
  # the following line skips the linter which checks for copyrights
  # comment the line when a copyright and license is added to all source files
  set(ament_cmake_copyright_FOUND TRUE)
  # the following line skips cpplint (only works in a git repo)
  # comment the line when this package is in a git repo and when
  # a copyright and license is added to all source files
  set(ament_cmake_cpplint_FOUND TRUE)
  ament_lint_auto_find_test_dependencies()
endif()

install(
  DIRECTORY description launch description
  DESTINATION share/${PROJECT_NAME}
)

install(DIRECTORY launch DESTINATION share/${PROJECT_NAME}/)

#install(TARGETS
#  lidar_node
#  DESTINATION lib/${PROJECT_NAME}
#)

ament_package()
