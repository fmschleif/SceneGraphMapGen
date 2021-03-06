
MIRA_REQUIRE_PACKAGE(SceneDesc)
MIRA_REQUIRE_PACKAGE(KinectDataTypes)
MIRA_REQUIRE_PACKAGE(RecognitionDataTypes)

###############################################################################

MIRA_ADD_DOCUMENTATION(SceneDesc
	DIRS
		doc
		include
	DEPENDS
        RecognitionDataTypes
)

###############################################################################

INCLUDE_DIRECTORIES(${CMAKE_CURRENT_LIST_DIR}/include)

###############################################################################

MIRA_ADD_LIBRARY(GraphMap
    SHARED
    PACKAGE SceneDesc
    SOURCE
        etc/GraphMap.xml
        src/GraphMap.C

    LINK_LIBS
        MIRABase
        MIRAFramework
        KinectDataTypes
        RecognitionDataTypes
        neo4j-client
)

set_target_properties(GraphMap PROPERTIES
	CXX_STANDARD 17
	CXX_EXTENSIONS OFF)
