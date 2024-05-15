cmake_minimum_required(VERSION 3.8)
project(kb_msgs)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

find_package(ament_cmake REQUIRED)

find_package(builtin_interfaces REQUIRED)

find_package(rosidl_default_generators REQUIRED)

rosidl_generate_interfaces(${PROJECT_NAME}
  "srv/Manage.srv"
  "srv/Revise.srv"
  "srv/Query.srv"
  "srv/About.srv"
  "srv/Lookup.srv"
  "srv/Event.srv"
  "srv/Sparql.srv"
  "msg/ActiveConcepts.msg"
  DEPENDENCIES builtin_interfaces
)

ament_export_dependencies(rosidl_default_runtime)

ament_package()

