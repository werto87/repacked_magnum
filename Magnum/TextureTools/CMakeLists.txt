target_sources(${TARGET_NAME} PRIVATE
Atlas.h
Atlas.cpp
visibility.h

)

if(MAGNUM_TARGET_GL)
target_sources(${TARGET_NAME} PRIVATE
    DistanceField.h 
    DistanceField.cpp    
    distancefieldconverter.cpp
    )
endif()

