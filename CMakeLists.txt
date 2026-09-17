# Created by Marcel Paz Goldschen-Ohm <marcel.goldschen@gmail.com>

# For macx xcode project: cmake -G Xcode <dir of CMakeLists.txt>

cmake_minimum_required(VERSION 3.21)

set(PROJECT_NAME QtPropertyEditor)
project(${PROJECT_NAME} LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(CMAKE_INCLUDE_CURRENT_DIR ON) # Search in current dir.
set(CMAKE_AUTOMOC ON) # Run moc automatically for Qt.
set(CMAKE_AUTOUIC ON) # Run uic automatically for *.ui files.
set(CMAKE_AUTORCC ON) # Run automatically for *.qrc files.

# Build project as a static library.
find_package(Qt6 COMPONENTS Widgets REQUIRED)

add_library(${PROJECT_NAME} STATIC QtPropertyEditor.cpp QtPropertyEditor.h)

target_link_libraries(${PROJECT_NAME} Qt6::Widgets)