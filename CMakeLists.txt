cmake_minimum_required(VERSION 3.2)

project(cmake VERSION 0.0.1)

find_package(Threads REQUIRED)


add_executable(helloworld main.cpp)


set_target_properties(helloworld PROPERTIES
    CXX_STANDARD 17
    CXX_STANDARD_REQUIRED ON
    COMPILE_OPTIONS "-Wpedantic;-Wall;-Wextra"
)



install(TARGETS helloworld RUNTIME DESTINATION bin)

set(CPACK_GENERATOR DEB)

set(CPACK_PACKAGE_VERSION_MAJOR "${PROJECT_VERSION_MAJOR}")
set(CPACK_PACKAGE_VERSION_MINOR "${PROJECT_VERSION_MINOR}")
set(CPACK_PACKAGE_VERSION_PATCH "${PROJECT_VERSION_PATCH}")


set(CPACK_DEBIAN_PACKAGE_SHLIBDEPS ON)

include(CPack)




