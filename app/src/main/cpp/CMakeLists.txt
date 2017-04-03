
cmake_minimum_required(VERSION 3.4.1)

add_library(app-glue STATIC ${ANDROID_NDK}/sources/android/native_app_glue/android_native_app_glue.c)

add_library(native-hunted SHARED  main.c)

target_include_directories(native-hunted PRIVATE ${ANDROID_NDK}/sources/android/native_app_glue)

# add lib dependencies
target_link_libraries(native-hunted
                      android
                      app-glue
                      log
                      m)
