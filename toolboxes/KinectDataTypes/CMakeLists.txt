
MIRA_REQUIRE_PACKAGE(KinectDataTypes)

###############################################################################

MIRA_ADD_DOCUMENTATION(KinectDataTypes
	DIRS
		doc
		include
	DEPENDS
		#RobotDataTypes
)

###############################################################################

MIRA_ADD_LIBRARY(KinectDataTypes
	SHARED
	PACKAGE KinectDataTypes
	SOURCE
		include/kinectdatatypes/KinectDataTypesExports.h
		include/kinectdatatypes/Types.h
		src/Types.C
		include/kinectdatatypes/RGBDQueue.h
		src/RGBDQueue.C
		include/kinectdatatypes/RGBDOperations.h
		src/RGBDOperations.C

	LINK_LIBS
		MIRABase
		MIRAFramework
		libfreenect2.so
)

set_target_properties(KinectDataTypes PROPERTIES
	CXX_STANDARD 17
	CXX_EXTENSIONS OFF)
