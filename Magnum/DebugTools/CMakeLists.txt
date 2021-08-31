target_sources(${TARGET_NAME} PRIVATE
DebugTools.h
Screenshot.cpp
CompareImage.h
FrameProfiler.h
FrameProfiler.cpp
visibility.h
ColorMap.cpp
ColorMap.h
Screenshot.h
CompareImage.cpp
)

if(MAGNUM_TARGET_GL)
target_sources(${TARGET_NAME} PRIVATE
ResourceManager.cpp
ResourceManager.h
ForceRenderer.h
ForceRenderer.cpp
BufferData.h
BufferData.cpp
TextureImage.h 
TextureImage.cpp
ObjectRenderer.cpp
ObjectRenderer.h
)
endif()




add_subdirectory(Implementation)
