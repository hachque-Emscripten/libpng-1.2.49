cmake_minimum_required(VERSION 2.6)
project(png)

# Ensure we are building against Emscripten.
if(NOT DEFINED EMSCRIPTEN_ACTIVE)
	message("Please run cmake with the -C $EMSCRIPTEN_ROOT/Emscripten.cmake option." FATAL_ERROR)
endif(NOT DEFINED EMSCRIPTEN_ACTIVE)

# Define project.
add_library(png
	src/pngerror.c
	src/pngmem.c
	src/pngread.c
	src/pngrtran.c
	src/pngset.c
	src/pngtrans.c
	src/pngwrite.c
	src/pngwutil.c
	src/png.c
	src/pngget.c
	src/pngpread.c
	src/pngrio.c
	src/pngrutil.c
	src/pngwio.c
	src/pngwtran.c
)
set_target_properties(png PROPERTIES SUFFIX ".js")
