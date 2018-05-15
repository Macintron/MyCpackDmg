cmake_minimum_required(VERSION 3.11)

project(MyCPackDmg)

add_executable(MyCPackApp MyCPackApp.cpp)
install(TARGETS MyCPackApp DESTINATION .)


set(CPACK_BINARY_DRAGNDROP ON)
set(CPACK_GENERATOR DragNDrop)
set(CPACK_PACKAGE_FILE_NAME "My-CPack-App-1.0.0")
set(CPACK_DMG_VOLUME_NAME "My CPack App")
set(CPACK_DMG_BACKGROUND_IMAGE "${CMAKE_CURRENT_SOURCE_DIR}/DiskImage/DMGBackground.png")
set(CPACK_PACKAGE_ICON "${CMAKE_CURRENT_SOURCE_DIR}/DiskImage/VolumeIcon.icns")

# next line disables package icon (volume icon)
set(CPACK_DMG_DS_STORE_SETUP_SCRIPT "${CMAKE_CURRENT_SOURCE_DIR}/DiskImage/adjust_dmg.scpt")

# DS_STORE: icon size and background image do not work.
#set(CPACK_DMG_DS_STORE "${CMAKE_CURRENT_SOURCE_DIR}/DiskImage/DS_Store")

include (CPack)
