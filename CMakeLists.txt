cmake_minimum_required(VERSION 3.10)

project(mdns_qt)

find_package(Qt5 COMPONENTS Core Network REQUIRED)

set(sources
	"${CMAKE_CURRENT_SOURCE_DIR}/dnspacket.cpp"
	"${CMAKE_CURRENT_SOURCE_DIR}/sbzeroconfservicediscovery.cpp"
	"${CMAKE_CURRENT_SOURCE_DIR}/sbzeroconfservicerecord.cpp"
)

set(headers
	"${CMAKE_CURRENT_SOURCE_DIR}/dnspacket.h"
	"${CMAKE_CURRENT_SOURCE_DIR}/sbzeroconfservicediscovery.h"
	"${CMAKE_CURRENT_SOURCE_DIR}/sbzeroconfservicerecord.h"
)

add_library(mdns_qt ${sources} ${headers})

target_link_libraries(mdns_qt PRIVATE Qt5::Core Qt5::Network)

install(TARGETS mdns_qt DESTINATION lib)
install(FILES ${headers} DESTINATION include/mdns_qt)
