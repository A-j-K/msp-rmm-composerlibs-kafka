
PROJECT("generic-kafka-webhook")

INCLUDE_DIRECTORIES(
	"${PROJECT_SOURCE_DIR}/lib"
)

SET(main_SRCS
        main.cpp
	event_cb.cpp
	consume_cb.cpp
)

ADD_EXECUTABLE("${PROJECT_NAME}"
        ${main_SRCS}
)

TARGET_LINK_LIBRARIES("${PROJECT_NAME}"
	kafka_utils_lib
)

INSTALL(PROGRAMS ${PROJECT_BINARY_DIR}/${PROJECT_NAME}
	DESTINATION /usr/bin
)
	
