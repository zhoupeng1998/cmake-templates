cmake_minimum_required( VERSION 3.16 )
project( Qt6Project VERSION 1.0.0 LANGUAGES CXX )

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(Qt6 REQUIRED COMPONENTS Core Widgets)
qt_standard_project_setup()

qt_add_resources(QRCS resources.qrc)

qt_add_executable(Qt6Project
    mainwindow.ui
    mainwindow.cpp
    main.cpp
    ${QRCS}
)

target_link_libraries(Qt6Project PRIVATE Qt6::Core Qt6::Widgets)

set_target_properties(Qt6Project PROPERTIES
    WIN32_EXECUTABLE ON
    MACOSX_BUNDLE ON
)
