cmake_minimum_required(VERSION 3.5)
PROJECT(sayhello)

INCLUDE_DIRECTORIES(${PROJECT_SOURCE_DIR}/include)
ADD_LIBRARY(hello SHARED ${PROJECT_SOURCE_DIR}/hello.c)

ADD_EXECUTABLE(sayhello useHello.c)
TARGET_LINK_LIBRARIES(sayhello hello)

INSTALL(TARGETS hello LIBRARY DESTINATION /usr/local/lib)
INSTALL(FILES ${PROJECT_SOURCE_DIR}/include/hello.h
		DESTINATION /usr/local/include)
