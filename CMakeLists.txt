cmake_minimum_required(VERSION 3.24)

option(CMAKE_COMPILE_WARNING_AS_ERROR "Enable warnings-as-error" ON)

project(stm32-devcontainer-template LANGUAGES C CXX ASM VERSION 1.0.0) # x-release-please-version

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED On)

set_directory_properties(PROPERTY USE_FOLDERS ON)

add_subdirectory(amp-embedded-infra-lib)
add_subdirectory(amp-hal-st)
add_subdirectory(source)

emil_clangformat_directories(stm32-devcontainer-template DIRECTORIES ./source)
emil_folderize_all_targets()
