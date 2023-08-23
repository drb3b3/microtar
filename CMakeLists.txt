cmake_minimum_required (VERSION 3.5)
project(microtar)

set(SOURCES src/microtar.c)

add_library(microtar_static STATIC ${SOURCES})
target_include_directories(microtar_static PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/src)

if (WIN32)
  target_link_options(microtar_static PUBLIC -static -static-libgcc -static-libstdc++)
endif ()
target_compile_options(microtar_static PUBLIC -Wall)
target_compile_options(microtar_static PUBLIC -Wextra)
target_compile_options(microtar_static PUBLIC -Wshadow)
target_compile_options(microtar_static PUBLIC -Wconversion)
target_compile_options(microtar_static PUBLIC -Wpedantic)
target_compile_options(microtar_static PUBLIC -Wshadow)
target_compile_options(microtar_static PUBLIC -fno-rtti)
