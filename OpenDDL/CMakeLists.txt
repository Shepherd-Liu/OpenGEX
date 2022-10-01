add_library(OpenDDL
ODDLMap.cpp
ODDLString.cpp
ODDLTree.cpp
OpenDDL.cpp
)

set(HEADER_FILES OpenDDL.h ODDLArray.h
    ODDLMap.h
    ODDLString.h
    ODDLTree.h
    ODDLTypes.h
    )
    
set(MYGE_EXTERNAL_ROOT ${PROJECT_BINARY_DIR}/../../${MYGE_TARGET_PLATFORM})

set_target_properties(OpenDDL
    PROPERTIES PUBLIC_HEADER "${HEADER_FILES}"
)

install(TARGETS OpenDDL
    ARCHIVE DESTINATION ${MYGE_EXTERNAL_ROOT}/lib
    PUBLIC_HEADER DESTINATION ${MYGE_EXTERNAL_ROOT}/include/OpenGEX
)

if(${MSVC})
    install(FILES ${PROJECT_BINARY_DIR}/OpenDDL/Debug/OpenDDL.pdb
        DESTINATION ${MYGE_EXTERNAL_ROOT}/lib/Debug
        CONFIGURATIONS Debug
        )
endif(${MSVC})

