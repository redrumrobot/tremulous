project(SDL2)

add_library(SDL2 INTERFACE IMPORTED)

set_property(TARGET SDL2 
    PROPERTY INTERFACE_INCLUDE_DIRECTORES
    "${CMAKE_SOURCE_DIR}/src/SDL2/include")

set_property(TARGET SDL2
    PROPERTY INTERFACE_LINK_LIBRARIES
    "libSDL2main.a"
    "libSDL2-2.0.0.dylib" )

set_property(TARGET SDL2
    PROPERTY INTERFACE_COMPILE_OPTIONS
    "-L${CMAKE_CURRENT_SOURCE_DIR}")

set_property(
    TARGET SDL2 
    APPEND PROPERTY INTERFACE_INCLUDE_DIRECTORIES
    $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>
    $<INSTALL_INTERFACE:>
    )

message(STATUS "
    ${lib}: LINK_INTERFACE_LIBRARIES = \"${lil}\"
    INTERFACE_LINK_LIBRARIES = \"${ill}\""
    )
