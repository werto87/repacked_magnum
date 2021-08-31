target_sources(${TARGET_NAME} PRIVATE
AbstractGlyphCache.h
AbstractFontConverter.cpp
Alignment.h
AbstractGlyphCache.cpp
AbstractFont.cpp
AbstractFontConverter.h
visibility.h
Text.h
AbstractFont.h
)


if(MAGNUM_TARGET_GL)
    target_sources(${TARGET_NAME} PRIVATE
    Renderer.h
    Renderer.cpp
    GlyphCache.cpp
    GlyphCache.h
    DistanceFieldGlyphCache.h
    DistanceFieldGlyphCache.cpp
    fontconverter.cpp
    )    
endif()

configure_file(${CMAKE_CURRENT_SOURCE_DIR}/configure.h.cmake
${CMAKE_CURRENT_BINARY_DIR}/configure.h)
