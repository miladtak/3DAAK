cmake_minimum_required(VERSION 3.16...3.28)

project(${TORQUE_APP_NAME})

file(GLOB_RECURSE GAME_SOURCES
    "*.cpp"
    "*.c"
)

add_executable(${TORQUE_APP_NAME} ${GAME_SOURCES})

target_link_libraries(${TORQUE_APP_NAME}
    OpenAL32
    SDL2main
)
