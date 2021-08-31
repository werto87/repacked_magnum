target_sources(${TARGET_NAME} PRIVATE
MagnumFontConverter.cpp
importStaticPlugin.cpp
MagnumFontConverter.h
)
configure_file(${CMAKE_CURRENT_SOURCE_DIR}/configure.h.cmake
${CMAKE_CURRENT_BINARY_DIR}/configure.h)
