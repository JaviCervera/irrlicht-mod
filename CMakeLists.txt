#Minimum version
cmake_minimum_required(VERSION 3.0)

#Define project
project(irrlicht)

#Define file groups
file(GLOB COMMON_FILES "source/Irrlicht/*.cpp" "source/Irrlicht/aesGladman/*.cpp" "source/Irrlicht/bzip2/*.c" "source/Irrlicht/jpeglib/*.c" "source/Irrlicht/libpng/*.c" "source/Irrlicht/lzma/*.c" "source/Irrlicht/zlib/*.c")
file(GLOB MAC_FILES "source/Irrlicht/MacOSX/*.mm")

#Add header and lib directories
include_directories(${INCLUDE_DIRECTORIES} ${CMAKE_CURRENT_SOURCE_DIR}/include ${CMAKE_CURRENT_SOURCE_DIR}/source/Irrlicht ${CMAKE_CURRENT_SOURCE_DIR}/source/Irrlicht/zlib)
#link_directories(${LINK_DIRECTORIES} ${CMAKE_CURRENT_SOURCE_DIR}/lib/irrlicht ${CMAKE_CURRENT_SOURCE_DIR}/lib/sdl)

#Add executable targets
if (${CMAKE_SYSTEM_NAME} MATCHES "Darwin")
	add_library(irrlicht_dll SHARED ${COMMON_FILES} ${MAC_FILES})
	add_library(irrlicht_lib STATIC ${COMMON_FILES} ${MAC_FILES})
else (${CMAKE_SYSTEM_NAME} MATCHES "Darwin")
	add_library(irrlicht_dll SHARED ${COMMON_FILES})
	add_library(irrlicht_lib STATIC ${COMMON_FILES})
endif (${CMAKE_SYSTEM_NAME} MATCHES "Darwin")

#Add common options
target_compile_definitions(irrlicht_lib PRIVATE ${COMPILE_DEFINITIONS} -D_IRR_STATIC_LIB_)
target_compile_definitions(irrlicht_dll PRIVATE ${COMPILE_DEFINITIONS} -D_USRDLL -DIRRLICHT_EXPORTS)
add_definitions(-U__STRICT_ANSI__)
set(CMAKE_CXX_FLAGS ${CMAKE_CXX_FLAGS} "-std=c++98 -fno-exceptions -fno-rtti -ffast-math -Wno-unused-parameter")

#Add platform specific options
if (${CMAKE_SYSTEM_NAME} MATCHES "Windows")
	message("Platform is Windows")
	add_definitions(-D__GNUWIN32__ -DWIN32 -D_WINDOWS -DNDEBUG -D_MBCS -D_CRT_SECURE_NO_DEPRECATE)
	set(CMAKE_CXX_FLAGS ${CMAKE_CXX_FLAGS} "-fno-exceptions")
	set(CMAKE_SHARED_LINKER_FLAGS ${CMAKE_SHARED_LINKER_FLAGS} "-s -static")
	target_link_libraries(irrlicht_dll -lkernel32 -luser32 -lgdi32 -lwinspool -lcomdlg32 -ladvapi32 -lshell32 -lole32 -loleaut32 -luuid -lwinmm -lopengl32 ${TARGET_LINK_LIBRARIES})
elseif (${CMAKE_SYSTEM_NAME} MATCHES "Darwin")
	message("Platform is macOS")
	set(CMAKE_SHARED_LINKER_FLAGS ${CMAKE_SHARED_LINKER_FLAGS} "-s")
	target_link_libraries(irrlicht_dll "-framework AppKit" "-framework Carbon" "-framework IOKit" "-framework OpenGL" ${TARGET_LINK_LIBRARIES})
elseif (${CMAKE_SYSTEM_NAME} MATCHES "Linux")
	message("Platform is Linux")
	set(CMAKE_CXX_FLAGS ${CMAKE_CXX_FLAGS} "-fno-exceptions")
	set(CMAKE_SHARED_LINKER_FLAGS ${CMAKE_SHARED_LINKER_FLAGS} "-s")
	target_link_libraries(irrlicht_dll -lGL -lXxf86vm ${TARGET_LINK_LIBRARIES})
else (${CMAKE_SYSTEM_NAME} MATCHES "Windows")
	message("Unrecognized platform " ${CMAKE_SYSTEM_NAME})
endif(${CMAKE_SYSTEM_NAME} MATCHES "Windows")
