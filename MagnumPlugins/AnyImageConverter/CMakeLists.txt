target_sources(${TARGET_NAME} PRIVATE
AnyImageConverter.h
AnyImageConverter.cpp
importStaticPlugin.cpp
)
configure_file(${CMAKE_CURRENT_SOURCE_DIR}/configure.h.cmake
${CMAKE_CURRENT_BINARY_DIR}/configure.h)
