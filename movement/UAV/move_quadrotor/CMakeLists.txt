## Minimum cmake version
cmake_minimum_required(VERSION 2.8.3)

## Project name
project(move_quadrotor)

## Link to required simulator
find_package(catkin REQUIRED COMPONENTS 
  roscpp 
  sim
)

## Include CRATES libraries
include_directories( 
  include
  ${catkin_INCLUDE_DIRS}
)

add_library(dronkey_nav
	src/Navigate.cpp
)
## The example executable
add_executable(move_quadrotor 
	main.cpp
)

## Link against CRATES libraries
target_link_libraries(move_quadrotor 
  ${catkin_LIBRARIES}
  dronkey_nav
)
