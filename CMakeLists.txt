cmake_minimum_required(VERSION 2.6)
set(CMAKE_MODULE_PATH "${CMAKE_CURRENT_SOURCE_DIR}/modules")
include(${CMAKE_CURRENT_SOURCE_DIR}/cmake/Rock.cmake)
rock_init(cmake 1.0)

set(CMAKE_FILES
    FindBoost.cmake
    FindGem.cmake
    FindNumpy.cmake
    FindRuby.cmake
    FindSISL.cmake
    ListMacros.cmake
    PythonBind.cmake
    PythonInstallPath.cmake
    Rock.cmake
    RockRuby.cmake
    rock-config.cmake
)

find_package(catkin QUIET)
if (catkin_FOUND)
    catkin_package(CFG_EXTRAS ${CMAKE_FILES})

    install(FILES ${CMAKE_FILES}
    DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/cmake)
endif (catkin_FOUND)

install(DIRECTORY cmake DESTINATION share/rock/cmake)



