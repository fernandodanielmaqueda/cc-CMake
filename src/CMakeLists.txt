# Filename: CMakeLists.txt / v2024.03.26-001, part of cc-CMake

add_subdirectory(program1)
add_subdirectory(program2)
add_subdirectory(program3)
add_subdirectory(program4)
add_subdirectory(shared)

set(EXECUTABLES_LIST ${EXECUTABLES_LIST} PARENT_SCOPE)
set(STATIC_LIBRARIES_LIST ${STATIC_LIBRARIES_LIST} PARENT_SCOPE)
set(SHARED_LIBRARIES_LIST ${SHARED_LIBRARIES_LIST} PARENT_SCOPE)