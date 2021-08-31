target_sources(${TARGET_NAME} PRIVATE
vertexFormatMapping.hpp
compressedPixelFormatMapping.hpp
pixelFormatMapping.hpp
ImageProperties.h
meshPrimitiveMapping.hpp
converterUtilities.h
meshIndexTypeMapping.hpp
)

if(CORRADE_TARGET_WINDOWS AND MAGNUM_BUILD_STATIC AND NOT CORRADE_TARGET_WINDOWS_RT)
    target_sources(${TARGET_NAME} PRIVATE
    WindowsWeakSymbol.h
    WindowsWeakSymbol.cpp
    )    
endif()

