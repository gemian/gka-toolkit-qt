cmake_minimum_required(VERSION 3.7)
project(gka-toolkit-qt)
string(TOLOWER ${PROJECT_NAME} PROJECT_NAME_LOWER)

set(CMAKE_CXX_STANDARD 14)
set(QT_MIN_VERSION "5.7.0")

find_package(ECM REQUIRED NO_MODULE)

set(CMAKE_MODULE_PATH ${ECM_MODULE_PATH} ${ECM_KDE_MODULE_DIR} "${CMAKE_SOURCE_DIR}/cmake")

find_package(Qt5 REQUIRED NO_MODULE COMPONENTS Core Quick Test Gui Widgets QuickControls2 Organizer)

include(KDEInstallDirs)
include(KDECMakeSettings)
include(ECMQueryQmake)
include(GenerateExportHeader)

add_definitions(-DPACKAGE_VERSION="0.1" -DPACKAGE_DATA_DIR="${CMAKE_INSTALL_PREFIX}/share/gka/toolkit-qt")
add_definitions(-DPACKAGE_QML_DIR="${KDE_INSTALL_QMLDIR}/org/gka/toolkit-qt")

add_subdirectory(src)
add_subdirectory(tests)
