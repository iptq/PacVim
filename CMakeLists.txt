cmake_minimum_required(VERSION 3.0)
project(pacvim "CXX")

set(THREADS_PREFER_PTHREAD_FLAG ON)

add_executable(pacvim
    src/avatar.cpp
    src/game.cpp
    src/ghost1.cpp
    src/globals.cpp
    src/helperFns.cpp
)

find_package(Curses REQUIRED)
find_package(Threads REQUIRED)

target_link_libraries(pacvim PUBLIC
    ${CURSES_LIBRARIES}
    Threads::Threads
)

target_include_directories(pacvim PUBLIC
    includes
    ${CURSES_INCLUDE_DIR}
)
