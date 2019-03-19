

cmake_minimum_required(VERSION 2.8)
include(${CMAKE_ROOT}/Modules/ExternalProject.cmake)

project(market_listener)



SET(MQTT_INCLUDE_DIR
${CMAKE_CURRENT_SOURCE_DIR}/inc/paho.mqtt.c-master)

set(MQTT
		"${MQTT_INCLUDE_DIR}"
		"${MQTT_INCLUDE_DIR}/src/MQTTClient.h"
)

INCLUDE_DIRECTORIES(${MQTT_INCLUDE_DIR}/src)
INCLUDE_DIRECTORIES(${MQTT_INCLUDE_DIR}/inc/paho.mqtt.c-master)


add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/inc/paho.mqtt.c-master)
add_executable(listener src/main.c)


install (TARGETS listener DESTINATION bin)
install (FILES "src/main.c" DESTINATION src)
