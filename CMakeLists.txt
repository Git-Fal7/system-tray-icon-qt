cmake_minimum_required (VERSION 3.8.2)
set(PROJECT pavutray)
project(${PROJECT})

# Find includes in the build directories
set(CMAKE_INCLUDE_CURRENT_DIR ON)

# Turn on automatic invocation of the MOC, UIC & RCC
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTOUIC ON)
set(CMAKE_AUTORCC ON)

# Add a compiler flag
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall")

# Find the QtWidgets library
find_package(Qt5 REQUIRED COMPONENTS Widgets)

# Tell CMake to create the executable
add_executable(${PROJECT} main.cpp mainwindow.cpp)

# Add the Qt5 Widgets for linking
target_link_libraries(${PROJECT} Qt5::Widgets)

install(TARGETS ${PROJECT} RUNTIME DESTINATION bin)
install(FILES "autostart/pavutray.desktop" DESTINATION "/etc/xdg/autostart")
