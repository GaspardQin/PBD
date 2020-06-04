#include_directories(${PROJECT_PATH}/extern/freeglut/include)

set(VIS_HEADER_FILES
	${PROJECT_PATH}/Visualization/MiniGL.h
	${PROJECT_PATH}/Visualization/Selection.h
	${PROJECT_PATH}/Visualization/Shader.h
	${PROJECT_PATH}/Visualization/Visualization.h
	) 

	
set(VIS_SOURCE_FILES
	${PROJECT_PATH}/Visualization/MiniGL.cpp                       
	${PROJECT_PATH}/Visualization/Shader.cpp
	) 
	

set(VIS_FILES
	${VIS_HEADER_FILES}
	${VIS_SOURCE_FILES}
	) 
#add_definitions(-std=c++11)

#find_package( Eigen3 REQUIRED )
#include_directories(${EIGEN3_INCLUDE_DIR} ${PROJECT_SOURCE_DIR})

#add_library(Visualization STATIC ${VIS_HEADER_FILES} ${VIS_SOURCE_FILES})
#set_target_properties(Visualization PROPERTIES FOLDER "External Dependencies")
#target_link_libraries(Visualization X11)


# A macro for the source groups
macro(VIS_SOURCE_GROUPS)
	source_group("Header Files\\Visualization" FILES ${VIS_HEADER_FILES})
	source_group("Source Files\\Visualization" FILES ${VIS_SOURCE_FILES})
endmacro(VIS_SOURCE_GROUPS)



