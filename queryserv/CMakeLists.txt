CMAKE_MINIMUM_REQUIRED(VERSION 3.12)

SET(qserv_sources
    database.cpp
    queryserv.cpp
    queryservconfig.cpp
    worldserver.cpp
    zonelist.cpp
    zoneserver.cpp
)

SET(qserv_headers
    database.h
    queryservconfig.h
    worldserver.h
    zonelist.h
    zoneserver.h
)

ADD_EXECUTABLE(queryserv ${qserv_sources} ${qserv_headers})

INSTALL(TARGETS queryserv RUNTIME DESTINATION ${CMAKE_INSTALL_PREFIX}/bin)

ADD_DEFINITIONS(-DQSERV)

TARGET_LINK_LIBRARIES(queryserv ${SERVER_LIBS})

SET(EXECUTABLE_OUTPUT_PATH ${PROJECT_BINARY_DIR}/bin)
