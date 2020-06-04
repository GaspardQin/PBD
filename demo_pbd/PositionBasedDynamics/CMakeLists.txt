add_library(PositionBasedDynamics
		${PROJECT_SOURCE_DIR}/Common/Common.h
		DirectPositionBasedSolverForStiffRodsInterface.h
		MathFunctions.cpp
		MathFunctions.h
		PositionBasedDynamics.cpp
		PositionBasedDynamics.h
		PositionBasedElasticRods.cpp
		PositionBasedElasticRods.h
		PositionBasedFluids.cpp
		PositionBasedFluids.h
		PositionBasedRigidBodyDynamics.cpp
		PositionBasedRigidBodyDynamics.h
		PositionBasedGenericConstraints.h
		SPHKernels.cpp
		SPHKernels.h
		TimeIntegration.cpp
		TimeIntegration.h
		
		CMakeLists.txt
)
add_definitions(-std=c++11)
find_package( Eigen3 REQUIRED )
include_directories( ${EIGEN3_INCLUDE_DIR} ${PROJECT_SOURCE_DIR} )

install(TARGETS PositionBasedDynamics
        RUNTIME DESTINATION bin
        LIBRARY DESTINATION lib
        ARCHIVE DESTINATION lib)

install(DIRECTORY .
DESTINATION include/PositionBasedDynamics
FILES_MATCHING PATTERN "*.h")




