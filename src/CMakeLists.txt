#
#      KCANVAS PROJECT
#
#  Common 2D graphics API abstraction with multiple back-end support
#
#  (c) livingcreative, 2015 - 2017
#
#  https://github.com/livingcreative/kcanvas
#
#  CMakeLists.txt
#      kcanvas API cmake project
#

cmake_minimum_required(VERSION 2.8)

project(kcanvas)

set(INCLUDE_PATH ../include/kcanvas)
set(HEADERS
	# public include headers
        ${INCLUDE_PATH}/canvas.h
        ${INCLUDE_PATH}/canvastypes.h
        ${INCLUDE_PATH}/canvasresources.h
        ${INCLUDE_PATH}/canvasplatform.h

	# private source headers
	canvasimpl.h
        win/canvasimpld2d.h
)

set(SOURCES
    win/canvasimpld2d.cpp
    win/platform.cpp
        # platform independend sources
	canvas.cpp
	canvastypes.cpp
	canvasimpl.cpp
)

if(WIN32)
    include(win/windows.cmake)
endif()

# public include directories
include_directories(${INCLUDE_PATH})

add_library(kcanvas STATIC ${SOURCES} ${HEADERS})
