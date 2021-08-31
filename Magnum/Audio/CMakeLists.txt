target_sources(${TARGET_NAME} PRIVATE
Buffer.cpp
Listener.h
Context.h
Listener.cpp
PlayableGroup.h
al-info.cpp
Renderer.cpp
PlayableGroup.cpp
BufferFormat.h
Renderer.h
AbstractImporter.h
visibility.h
Source.cpp
Context.cpp
Audio.h
Playable.h
AbstractImporter.cpp
Buffer.h
BufferFormat.cpp
Source.h
Playable.cpp
Audio.cpp
)

if(WITH_AUDIO)
    target_sources(${TARGET_NAME} PRIVATE
    Extensions.h
    )
endif()


configure_file(${CMAKE_CURRENT_SOURCE_DIR}/configure.h.cmake
${CMAKE_CURRENT_BINARY_DIR}/configure.h)
