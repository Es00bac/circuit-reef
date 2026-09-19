# SPDX-License-Identifier: GPL-3.0-or-later
find_package(Qt6 6.4 REQUIRED COMPONENTS Core Gui Quick Qml)
add_library(circuit-reef-qt STATIC CircuitReefItem.cpp CircuitReefItem.hpp)
set_target_properties(circuit-reef-qt PROPERTIES AUTOMOC ON)
target_include_directories(circuit-reef-qt PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
target_link_libraries(circuit-reef-qt PUBLIC reef-core Qt6::Core Qt6::Gui Qt6::Quick Qt6::Qml)
add_executable(circuit-reef-qt-preview preview.cpp)
target_link_libraries(circuit-reef-qt-preview PRIVATE circuit-reef-qt)
