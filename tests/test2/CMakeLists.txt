# Filename: CMakeLists.txt / v2024.03.26-001, part of cc-CMake

set(TEST2 test2)
add_executable(${TEST2})
file(GLOB_RECURSE TEST2_SOURCES "src/*.c")
target_sources(${TEST2} PRIVATE ${TEST2_SOURCES})
add_dependencies(${TEST2} Unity)
target_compile_features(${TEST2} PUBLIC c_std_99)
# target_precompile_headers(${TEST2} PRIVATE)
target_include_directories(${TEST2} BEFORE PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
target_link_directories(${TEST2} BEFORE PUBLIC "${PROJECT_SOURCE_DIR}/build/${CMAKE_HOST_SYSTEM_NAME}/thirdparty/unity/lib")
# target_compile_definitions(${TEST2} PUBLIC)
target_compile_options(${TEST2} PUBLIC "")
target_link_options(${TEST2} BEFORE PUBLIC "")
target_link_libraries(${TEST2} PUBLIC "m" PUBLIC "unity" PRIVATE "")

add_test(
    NAME "Test2"
    COMMAND ${TEST2}
    WORKING_DIRECTORY ${CMAKE_BINARY_DIR}
)