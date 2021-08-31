target_sources(${TARGET_NAME} PRIVATE
WavHeader.cpp
WavImporter.cpp
WavHeader.h
importStaticPlugin.cpp
WavImporter.h
)
configure_file(${CMAKE_CURRENT_SOURCE_DIR}/configure.h.cmake
${CMAKE_CURRENT_BINARY_DIR}/configure.h)
