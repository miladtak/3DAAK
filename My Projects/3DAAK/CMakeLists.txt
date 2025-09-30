cmake_minimum_required(VERSION 3.16)

# تعریف نام پروژه با استفاده از متغیر TORQUE_APP_NAME
project(${TORQUE_APP_NAME}_game)

# تنظیم مسیر فایل‌های سورس فقط از همین پوشه، نه کل پروژه
file(GLOB GAME_SOURCES
    "${CMAKE_CURRENT_SOURCE_DIR}/*.cpp"
    "${CMAKE_CURRENT_SOURCE_DIR}/*.c"
)

# بررسی اینکه فایل سورس واقعاً پیدا شده
if(NOT GAME_SOURCES)
    message(FATAL_ERROR "No source files found in ${CMAKE_CURRENT_SOURCE_DIR}")
endif()

# ساخت فایل اجرایی
add_executable(${TORQUE_APP_NAME}_game ${GAME_SOURCES})

# لینک کردن کتابخانه‌های مورد نیاز
target_link_libraries(${TORQUE_APP_NAME}_game
    OpenAL32
    SDL2main
)

# تنظیمات اضافی برای ویندوز
if(WIN32)
    target_compile_definitions(${TORQUE_APP_NAME}_game PRIVATE _CRT_SECURE_NO_WARNINGS)
endif()
