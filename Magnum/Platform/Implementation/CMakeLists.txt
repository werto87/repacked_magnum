target_sources(${TARGET_NAME} PRIVATE
DpiScaling.h
AbstractContextHandler.h
DpiScaling.cpp
)

if(MAGNUM_TARGET_GL)
    target_sources(${TARGET_NAME} PRIVATE
    Egl.h
    EglContextHandler.h
    Egl.cpp
    EglContextHandler.cpp
    GlxContextHandler.cpp
    OpenGLFunctionLoader.cpp
    GlxContextHandler.h
    OpenGLFunctionLoader.h
    )
endif()