cmake_minimum_required(VERSION 2.8.3)
project(dynamic_graph_bridge_msgs)

find_package(catkin REQUIRED COMPONENTS message_generation std_msgs)

add_message_files(
  DIRECTORY msg
  FILES
  Matrix.msg
  Vector.msg
)

add_service_files(
  DIRECTORY srv
  FILES
  RunCommand.srv
  RunPythonFile.srv
)

generate_messages(DEPENDENCIES std_msgs)

catkin_package()

install(DIRECTORY include/${PROJECT_NAME}/
  DESTINATION ${CATKIN_PACKAGE_INCLUDE_DESTINATION}
  FILES_MATCHING PATTERN "*.h")
