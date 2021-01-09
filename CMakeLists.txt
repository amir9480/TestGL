cmake_minimum_required(VERSION 3.0.0)
project(TestGL VERSION 0.1.0)

include(CTest)
enable_testing()

include_directories("${CMAKE_CURRENT_SOURCE_DIR}/thirdparty/glad/include")
include_directories("${CMAKE_CURRENT_SOURCE_DIR}/thirdparty/glfw/include")

add_executable(
    TestGL
    main.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/thirdparty/glad/src/glad.c
)

target_link_libraries(
    TestGL
    # ${CMAKE_CURRENT_SOURCE_DIR}/thirdparty/mesa-build/lib-vc2019/opengl32.lib
    ${CMAKE_CURRENT_SOURCE_DIR}/thirdparty/glfw/lib-vc2019/glfw3.lib
)

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)
