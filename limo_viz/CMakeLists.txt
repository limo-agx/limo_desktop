cmake_minimum_required(VERSION 3.0.2)
project(limo_viz)

find_package(catkin REQUIRED)

catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES defense_viz
#  CATKIN_DEPENDS other_catkin_pkg
#  DEPENDS system_lib
)

include_directories(
# include
# ${catkin_INCLUDE_DIRS}
)

install(DIRECTORY launch rviz
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)

if (CATKIN_ENABLE_TESTING)
  find_package(roslaunch REQUIRED)
  roslaunch_add_file_check(launch/view_ackerman_model.launch)
  roslaunch_add_file_check(launch/view_four_diff_model.launch)
  roslaunch_add_file_check(launch/view_navigation_gmapping.launch)
  roslaunch_add_file_check(launch/view_navigation_rtabmap.launch)
  roslaunch_add_file_check(launch/view_robot.launch)
endif()
