cmake_minimum_required (VERSION 2.8.11)
project (PBD)


# Utils
add_subdirectory(Utils)

# Visualization
add_subdirectory(Visualization)

# AntTweakBar
add_subdirectory(extern/AntTweakBar)

# Simulation
add_subdirectory(Simulation) 

# PositionBasedDynamics
add_subdirectory(PositionBasedDynamics)

# for demo
set(DEMO_PBD_SRC
    demo_pbd/main.cpp
    demo_pbd/objloader.cpp
    Common/DemoBase.cpp
    Common/TweakBarParameters.cpp
)
add_definitions(-std=c++11)
find_package( Eigen3 REQUIRED )
include_directories( ${EIGEN3_INCLUDE_DIR} ${PROJECT_SOURCE_DIR})
add_executable(Demo_PBD ${DEMO_PBD_SRC} ${VIS_FILES})
add_dependencies(Demo_PBD Utils AntTweakBar Simulation)
target_link_libraries(Demo_PBD X11 Utils AntTweakBar Simulation)

