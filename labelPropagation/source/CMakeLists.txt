cmake_minimum_required(VERSION 2.8)

PROJECT( labelPropagation )

FIND_PACKAGE( OpenCV REQUIRED )

FIND_PACKAGE( VTK REQUIRED )
INCLUDE(${VTK_USE_FILE})

FIND_PACKAGE( ITK REQUIRED )
INCLUDE(${ITK_USE_FILE})

SET(SOURCES
	Utilities.h
	Utilities.cpp
	stdafx.h 
	stdafx.cpp
	main.cpp 
)

ADD_EXECUTABLE( labelPropagation ${SOURCES})
MESSAGE("${OpenCV_LIBS}")
TARGET_LINK_LIBRARIES( labelPropagation ${OpenCV_LIBS} )
TARGET_LINK_LIBRARIES( labelPropagation ${ITK_LIBRARIES} )
TARGET_LINK_LIBRARIES( labelPropagation ${VTK_LIBRARIES} )