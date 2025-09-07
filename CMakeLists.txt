cmake_minimum_required(VERSION 4.0.0)
project(synclet LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(DAEMON_EXEC ${PROJECT_NAME}-daemon)
set(CLI_EXEC ${PROJECT_NAME}-cli)

file(GLOB_RECURSE DAEMON_SOURCES src/daemon/*.cpp)
file(GLOB_RECURSE CLI_SOURCES src/cli/*.cpp)

add_executable(${DAEMON_EXEC} ${DAEMON_SOURCES})
target_include_directories(${DAEMON_EXEC} PRIVATE include/daemon)

add_executable(${CLI_EXEC} ${CLI_SOURCES})
target_include_directories(${CLI_EXEC} PRIVATE include/cli)