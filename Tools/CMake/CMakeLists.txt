# -----------------------------------------------------------------------------
# Copyright (c) 2014 GarageGames, LLC
# [متن مجوز بدون تغییر]
# -----------------------------------------------------------------------------

# ✅ نسخه CMake جدید برای سازگاری با GitHub Actions
cmake_minimum_required(VERSION 3.16...3.28)

# ✅ فعال‌سازی سیاست‌های جدید برای جلوگیری از خطاهای نسخه
if(POLICY CMP0074)
  cmake_policy(SET CMP0074 NEW)
endif()

if(POLICY CMP0091)
  cmake_policy(SET CMP0091 NEW)
endif()

# ✅ ادامه تنظیمات اصلی
include(basics.cmake)

setupVersionNumbers()

# the main engine, should come last
include(torque3d.cmake)

#setupPackaging()
