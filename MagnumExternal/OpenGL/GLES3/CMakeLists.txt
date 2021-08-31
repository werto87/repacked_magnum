target_sources(${TARGET_NAME} PRIVATE
flextGLPlatformIOS.cpp
flextGLPlatform.cpp
flextGL.h
flextGLWindowsDesktop.h
flextGL.cpp
flextGLWindowsDesktop.cpp
flextGLPlatformWindowsDesktop.cpp
flextGLEmscripten.h
)
add_subdirectory(Emscripten)
