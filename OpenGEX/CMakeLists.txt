add_library(OpenGEX
OpenGEX.cpp
)

include_directories(
${CMAKE_CURRENT_SOURCE_DIR}/../OpenDDL
)

set_target_properties(OpenGEX
PROPERTIES PUBLIC_HEADER OpenGEX.h
)

install(TARGETS OpenGEX
    ARCHIVE DESTINATION ${MYGE_EXTERNAL_ROOT}/lib
    PUBLIC_HEADER DESTINATION ${MYGE_EXTERNAL_ROOT}/include
)

if(${MSVC})
    install(FILES ${PROJECT_BINARY_DIR}/OpenGEX/Debug/OpenGEX.pdb
        DESTINATION ${MYGE_EXTERNAL_ROOT}/lib
        CONFIGURATIONS Debug
        )
endif(${MSVC})


