cmake_minimum_required(VERSION 3.0.2)
project(braccio_upload)

## Find catkin macros and libraries
find_package(catkin REQUIRED COMPONENTS roscpp sensor_msgs)

###################################
## catkin specific configuration ##
###################################
## The catkin_package macro generates cmake config files for your package
## Declare things to be passed to dependent projects
## INCLUDE_DIRS: uncomment this if your package contains header files
## LIBRARIES: libraries you create in this project that dependent projects also need
## CATKIN_DEPENDS: catkin_packages dependent projects also need
## DEPENDS: system dependencies of this project that dependent projects also need

catkin_package()

include_directories(include ${catkin_INCLUDE_DIRS})

install(DIRECTORY launch rviz parse_and_publish
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION})

add_executable(parse_and_publish parse_and_publish/parse_and_publish.cpp)
target_link_libraries(parse_and_publish ${catkin_LIBRARIES})
## add_dependencies(parse_and_publish std_msgs)
