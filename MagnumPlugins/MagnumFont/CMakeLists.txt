target_sources(${TARGET_NAME} PRIVATE
importStaticPlugin.cpp
)

if(MAGNUM_TARGET_GL)
    target_sources(${TARGET_NAME} PRIVATE
    MagnumFont.h
    MagnumFont.cpp    
    )
endif()

configure_file(${CMAKE_CURRENT_SOURCE_DIR}/configure.h.cmake
${CMAKE_CURRENT_BINARY_DIR}/configure.h)
