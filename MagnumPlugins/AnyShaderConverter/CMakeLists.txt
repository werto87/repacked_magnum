target_sources(${TARGET_NAME} PRIVATE
AnyConverter.cpp
AnyConverter.h
importStaticPlugin.cpp
)
configure_file(${CMAKE_CURRENT_SOURCE_DIR}/configure.h.cmake
${CMAKE_CURRENT_BINARY_DIR}/configure.h)
