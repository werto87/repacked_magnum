target_sources(${TARGET_NAME} PRIVATE
Stage.cpp
visibility.h
AbstractConverter.h
shaderconverter.cpp
Stage.h
AbstractConverter.cpp
ShaderTools.h
)
add_subdirectory(Implementation)
configure_file(${CMAKE_CURRENT_SOURCE_DIR}/configure.h.cmake
${CMAKE_CURRENT_BINARY_DIR}/configure.h)
