cmake_minimum_required(VERSION 3.28)
project(cpp_project)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED TRUE)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/bin")
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/lib") 
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/lib")

# add -Werror
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS}")

# Mac needed variables (adapt according to your needs)
set(CMAKE_MACOSX_RPATH ON)
#set(CMAKE_SKIP_BUILD_RPATH FALSE)
#set(CMAKE_BUILD_WITH_INSTALL_RPATH FALSE)
#set(CMAKE_INSTALL_RPATH "${CMAKE_INSTALL_PREFIX}/lib")
#set(CMAKE_INSTALL_RPATH_USE_LINK_PATH TRUE)

# add -Werror
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Werror")

# defines
set(VERSION_MAJOR "0")
set(VERSION_MINOR "1")
set(VERSION_PATCH "0")
set(VERSION ${VERSION_MAJOR}.${VERSION_MINOR}.${VERSION_PATCH})
set(RES_PATH "${CMAKE_BINARY_DIR}/res")

option(BUILD_TESTS "Build tests" OFF)

add_subdirectory(src)
add_subdirectory(include)
add_subdirectory(res)

# testing
if (BUILD_TESTS)
    add_subdirectory(tests)
endif(BUILD_TESTS)