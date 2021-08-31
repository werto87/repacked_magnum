target_sources(${TARGET_NAME} PRIVATE
Interleave.h
Combine.cpp
GenerateNormals.cpp
Tipsify.h
RemoveDuplicates.h
Reference.cpp
sceneconverter.cpp
Combine.h
FlipNormals.h
Reference.h
visibility.h
CompressIndices.h
Interleave.cpp
CompressIndices.cpp
Subdivide.h
Concatenate.cpp
GenerateIndices.cpp
Duplicate.h
FlipNormals.cpp
GenerateFlatNormals.h
Transform.h
RemoveDuplicates.cpp
Concatenate.h
GenerateNormals.h
GenerateIndices.h
Tipsify.cpp
Duplicate.cpp
)

if(MAGNUM_TARGET_GL)
    target_sources(${TARGET_NAME} PRIVATE
    Compile.cpp
    Compile.h
    FullScreenTriangle.h
    FullScreenTriangle.cpp
    )    
endif()






add_subdirectory(Implementation)
