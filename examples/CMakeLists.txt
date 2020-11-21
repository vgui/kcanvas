#
#      KCANVAS PROJECT
#
#  Common 2D graphics API abstraction with multiple back-end support
#
#  (c) livingcreative, 2015 - 2017
#
#  https://github.com/livingcreative/kcanvas
#
#  examples/CMakeLists.txt
#      kcanvas API examples cmake project
#

cmake_minimum_required(VERSION 2.8)

project(kcanvasexamples)


set(HEADERS
	# public include headers
        ../include/kcanvas/canvas.h

	# private source headers
	common/example.h
	common/bmp.h
)

set(SOURCES
	# platform independend sources
	common/bmp.cpp
        common/win/main.cpp
)

set(LIBS
	# kcanvas library
	kcanvas
)

# public include directories
include_directories(../include)

# basic shapes demo
add_executable(basicshapes ${SOURCES} "01basicshapes.cpp" ${HEADERS})
target_link_libraries(basicshapes ${LIBS})

# basic filled shapes demo
add_executable(basicfilledshapes ${SOURCES} "02basicfilledshapes.cpp" ${HEADERS})
target_link_libraries(basicfilledshapes ${LIBS})

# text and fonts demo
add_executable(textandfonts ${SOURCES} "03textandfonts.cpp" ${HEADERS})
target_link_libraries(textandfonts ${LIBS})

# paths demo
add_executable(paths ${SOURCES} "04paths.cpp" ${HEADERS})
target_link_libraries(paths ${LIBS})

# bitmaps demo
add_executable(bitmaps ${SOURCES} "05bitmaps.cpp" ${HEADERS})
target_link_libraries(bitmaps ${LIBS})

# gradients demo
add_executable(gradients ${SOURCES} "06gradients.cpp" ${HEADERS})
target_link_libraries(gradients ${LIBS})

# stroke styles demo
add_executable(strokestyles ${SOURCES} "07strokestyles.cpp" ${HEADERS})
target_link_libraries(strokestyles ${LIBS})

# clipping and masking demo
add_executable(clippingandmasking ${SOURCES} "08clippingandmasking.cpp" ${HEADERS})
target_link_libraries(clippingandmasking ${LIBS})
