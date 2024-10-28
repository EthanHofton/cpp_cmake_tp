# INCLUDE FOR FETCH CONTENT
# include(FetchContent)

# EXAMPLE: Fetch a project from githup (CLI11)
# FetchContent_Declare(
#     cli11_proj
#     QUIET
#     GIT_REPOSITORY https://github.com/CLIUtils/CLI11.git
#     GIT_TAG v2.3.2
# )
# FetchContent_MakeAvailable(cli11_proj)

# SET SOURCES
set(SRCS
    main.cpp
)

# Set program name
set(PROG_NAME "example")

add_executable(${PROG_NAME} ${SRCS})

target_link_libraries(${PROG_NAME})

target_include_directories(${PROG_NAME} PUBLIC
    ${PROJECT_SOURCE_DIR}/include
    ${PROJECT_BINARY_DIR}/include   # add the binary tree to the search path so that we will find Version.h
)