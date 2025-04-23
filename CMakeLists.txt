cmake_minimum_required(VERSION 3.14 FATAL_ERROR)

project(cpm_helloworld)

include(cmake/CPM.cmake)

# ---- Dependencies ----
CPMAddPackage("gh:nlohmann/json@3.11.3")
CPMAddPackage(
    NAME jsoncpp
    GITHUB_REPOSITORY open-source-parsers/jsoncpp
    GIT_TAG 1.9.5
    OPTIONS "JSONCPP_WITH_TESTS OFF"
)
# CPMAddPackage("gh:open-source-parsers/jsoncpp#1.9.5")
# ---- Executable ----

# CPMAddPackage(
#   NAME lua
#   GIT_REPOSITORY https://github.com/lua/lua.git
#   VERSION 5.3.5
#   DOWNLOAD_ONLY YES
# )


add_executable(jsontest main.cpp)
target_link_libraries(jsontest nlohmann_json jsoncpp_lib)
