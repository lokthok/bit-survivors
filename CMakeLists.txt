cmake_minimum_required(VERSION 3.16)
project(bit_survivors LANGUAGES C CXX)   # C wird für glad.c gebraucht

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# GLFW: Fenster, Tastatur und Maus. Nur die Bibliothek bauen, ohne Doku, Tests und Beispiele
set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)
set(GLFW_INSTALL OFF CACHE BOOL "" FORCE)
add_subdirectory(external/glfw)

# GLM: Mathe für Vektoren und Matrizen, besteht nur aus Headern
set(GLM_BUILD_LIBRARY OFF CACHE BOOL "" FORCE)
add_subdirectory(external/glm)

# Das Spiel
add_executable(game
    src/main.cpp
    external/glad/src/glad.c
)
target_include_directories(game PRIVATE external/glad/include)   # findet glad/glad.h und KHR/
target_link_libraries(game PRIVATE glfw glm::glm)