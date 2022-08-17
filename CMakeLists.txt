cmake_minimum_required(VERSION 3.16)
project("pybind11youtube")
set(CMAKE_CXX_STANDARD 17)

set(APP_SOURCE "${PROJECT_SOURCE_DIR}/Main")
set(EXTERNALS "${PROJECT_SOURCE_DIR}/externals")

# pybind11
add_subdirectory(${EXTERNALS}/pybind11)

add_executable (
    final
    ${APP_SOURCE}/main.cpp
)

target_include_directories (
    final
    PRIVATE ${APP_SOURCE}
)

target_link_libraries(
    final
    PRIVATE pybind11::embed
)