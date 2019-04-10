cmake_minimum_required( VERSION 3.13.0 )

project(qtpromise VERSION 0.5 LANGUAGES CXX)

include(GNUInstallDirs)

add_library(qtpromise INTERFACE)

target_include_directories(qtpromise INTERFACE $<INSTALL_INTERFACE:${CMAKE_INSTALL_INCLUDEDIR}/>)

install(DIRECTORY include       DESTINATION ${CMAKE_INSTALL_PREFIX})
install(DIRECTORY src           DESTINATION ${CMAKE_INSTALL_PREFIX})

install(TARGETS qtpromise EXPORT qtpromiseConfig
    DESTINATION ${CMAKE_INSTALL_LIBDIR})

install(EXPORT qtpromiseConfig
    DESTINATION "${CMAKE_INSTALL_LIBDIR}/cmake/qtpromise")
