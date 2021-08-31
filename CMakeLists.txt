cmake_minimum_required(VERSION 3.17)
project(project VERSION 1.0.0
  DESCRIPTION project
  LANGUAGES CXX
  ) 
cmake_policy(SET CMP0015 NEW)


########## enable cache system
include(cmake/Cache.cmake)

########## link against the libs to apply the configurations to the target
# compiler warnings
set(PROJECT_WARNINGS project_warning)
add_library(${PROJECT_WARNINGS} INTERFACE)
include(cmake/CompilerWarnings.cmake)
set_project_warnings(${PROJECT_WARNINGS})
# compiler options
set(PROJECT_OPTIONS project_options)


add_library(${PROJECT_OPTIONS} INTERFACE)
target_compile_features(${PROJECT_OPTIONS} INTERFACE cxx_std_20)


if(CMAKE_SYSTEM_NAME STREQUAL Emscripten)
    set(CORRADE_TARGET_EMSCRIPTEN 1)
    # It's meaningless to use dynamic libraries with Emscripten
    set(BUILD_STATIC ON)
elseif(UNIX)
    # Both APPLE and UNIX are defined on OSX
    if(APPLE)
        set(CORRADE_TARGET_APPLE 1)

        if(CMAKE_OSX_SYSROOT MATCHES "/iPhoneOS[0-9.]*\\.sdk")
            set(CORRADE_TARGET_IOS 1)
        elseif(CMAKE_OSX_SYSROOT MATCHES "/iPhoneSimulator[0-9.]*\\.sdk")
            set(CORRADE_TARGET_IOS 1)
            set(CORRADE_TARGET_IOS_SIMULATOR 1)
        endif()
    endif()

    # UNIX is also defined on Android
    if(CMAKE_SYSTEM_NAME STREQUAL Android)
        set(CORRADE_TARGET_ANDROID 1)
        # It's too inconvenient to manually load all shared libs using JNI
        set(BUILD_STATIC ON)
    endif()

    # Emscripten is Unix too, this selects only the other ones
    set(CORRADE_TARGET_UNIX 1)
elseif(WIN32)
    set(CORRADE_TARGET_WINDOWS 1)

    if(WINDOWS_PHONE OR WINDOWS_STORE)
        set(CORRADE_TARGET_WINDOWS_RT 1)
    endif()
endif()

# include(cmake/Sanitizers.cmake)
# enable_sanitizers(${PROJECT_OPTIONS})

# allow for static analysis options
# include(cmake/StaticAnalyzers.cmake) 
 
######## conan setup
include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
conan_basic_setup(TARGETS)


set(TARGET_NAME magnum)
add_library(${TARGET_NAME})
add_subdirectory(Magnum)
add_subdirectory(MagnumPlugins)
######## add sub dir



####### link
target_include_directories(${TARGET_NAME} PRIVATE ${CMAKE_CURRENT_BINARY_DIR})
target_include_directories(${TARGET_NAME} PRIVATE
  $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>
  $<INSTALL_INTERFACE:${CMAKE_INSTALL_INCLUDEDIR}>
  )
  




if(WITH_SDL2APPLICATION)
    target_link_libraries(${TARGET_NAME} PRIVATE
    CONAN_PKG::sdl
    )
endif()

if(WITH_GL)
    target_link_libraries(${TARGET_NAME} PRIVATE
    CONAN_PKG::gl
    )
endif()

if(WITH_VK)
    target_link_libraries(${TARGET_NAME} PRIVATE
    CONAN_PKG::vulkan-headers
    )
endif()

if(WITH_AUDIO)
    target_link_libraries(${TARGET_NAME} PRIVATE
    CONAN_PKG::openal
    )
endif()

target_link_libraries(${TARGET_NAME} PRIVATE
${PROJECT_WARNINGS}
${PROJECT_OPTIONS}
CONAN_PKG::repacked_corrade    
)






