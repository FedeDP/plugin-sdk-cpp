cmake_minimum_required(VERSION 3.8)

project(PluginSdkCPP VERSION 0.1.0 LANGUAGES CXX)

file(GLOB PUBLIC_H "include/*.h")

add_library(${PROJECT_NAME} INTERFACE)
target_include_directories(${PROJECT_NAME} INTERFACE include/)

set_target_properties(
    ${PROJECT_NAME} PROPERTIES 
    VERSION ${PROJECT_VERSION}
    SOVERSION ${PROJECT_VERSION_MAJOR}
    PUBLIC_HEADER "${PUBLIC_H}"
)

install(TARGETS ${PROJECT_NAME}
    PUBLIC_HEADER DESTINATION ${CMAKE_INSTALL_INCLUDEDIR}/
)
