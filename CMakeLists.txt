cmake_minimum_required(VERSION 3.0.0)
project(qtpixeldemo)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -pthread")
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)

find_package(Qt5 COMPONENTS Widgets Gui REQUIRED)

add_executable(qtpixeldemo
  mywidget.cpp
  test.cpp
  mlx90640_driver.cpp
)

target_link_libraries(qtpixeldemo Qt5::Widgets)
target_link_libraries(qtpixeldemo Qt5::Gui)
target_link_libraries(qtpixeldemo qwt-qt5)


install(TARGETS qtpixeldemo)

