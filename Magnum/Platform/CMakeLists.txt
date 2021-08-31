target_sources(${TARGET_NAME} PRIVATE
Platform.h
Screen.h
WindowlessIosApplication.h
ScreenedApplication.hpp

ScreenedApplication.h

WebApplication.css
)

if(WITH_SDL2APPLICATION)
    target_sources(${TARGET_NAME} PRIVATE
    Sdl2Application.h
    Sdl2Application.cpp
    )
endif()


if(MAGNUM_TARGET_GL)
    target_sources(${TARGET_NAME} PRIVATE
    gl-info.cpp
    AbstractXApplication.h
    AbstractXApplication.cpp
    WindowlessGlxApplication.cpp
    WindowlessGlxApplication.h
    WindowlessEglApplication.cpp
    XEglApplication.cpp 
    WindowlessWglApplication.cpp 
    GlxApplication.cpp 
    WindowlessCglApplication.h 
    WindowlessWglApplication.h 
    WindowlessWindowsEglApplication.cpp 
    XEglApplication.h 
    GlfwApplication.cpp 
    GlfwApplication.h 
    WindowlessCglApplication.cpp 
    WindowlessEglApplication.h 
    GlxApplication.h 
    WindowlessWindowsEglApplication.h 
    GLContext.h
    )
endif()

if(MAGNUM_TARGET_GL)
    target_sources(${TARGET_NAME} PRIVATE
    gl-info.cpp
    AbstractXApplication.h
    AbstractXApplication.cpp
    WindowlessGlxApplication.cpp
    WindowlessGlxApplication.h
    WindowlessEglApplication.cpp
    XEglApplication.cpp 
    WindowlessWglApplication.cpp 
    GlxApplication.cpp 
    WindowlessCglApplication.h 
    WindowlessWglApplication.h 
    WindowlessWindowsEglApplication.cpp 
    XEglApplication.h 
    GlfwApplication.cpp 
    GlfwApplication.h 
    WindowlessCglApplication.cpp 
    WindowlessEglApplication.h 
    GlxApplication.h 
    WindowlessWindowsEglApplication.h 
    GLContext.h
    )
endif()


if(CORRADE_TARGET_EMSCRIPTEN)
    target_sources(${TARGET_NAME} PRIVATE
    EmscriptenApplication.h
    EmscriptenApplication.cpp    
    )
endif()

if(CORRADE_TARGET_ANDROID)
    target_sources(${TARGET_NAME} PRIVATE
    AndroidApplication.h
    AndroidApplication.cpp
    )
endif()


add_subdirectory(Implementation)
