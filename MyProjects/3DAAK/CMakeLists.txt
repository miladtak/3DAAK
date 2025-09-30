# تنظیم نام پروژه
project(3DAAK_Game)

# اضافه کردن فایل‌های سورس
set(GAME_SOURCES
    main.cpp
)

# ساخت فایل اجرایی
add_executable(${TORQUE_APP_NAME}_game ${GAME_SOURCES})

# لینک کردن کتابخانه‌های لازم
target_link_libraries(${TORQUE_APP_NAME}_game
    SDL2main
    SDL2
    OpenAL32
)

# تنظیمات اضافی برای ویندوز
if(WIN32)
    target_compile_definitions(${TORQUE_APP_NAME}_game PRIVATE _CRT_SECURE_NO_WARNINGS)
endif()
