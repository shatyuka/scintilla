cmake_minimum_required(VERSION 3.10)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

project(Scintilla
        VERSION 5.5.8
        LANGUAGES CXX
)

add_subdirectory(src)
add_subdirectory(qt)
