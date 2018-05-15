# MyCpackDmg
CPack can't create adjusted window AND custom volume icon

## Description
When customising a disk image with CMake/CPack/DragNDrop on Mac, it is kind of impossible to have an adjusted window/icons AND a custom volume icon.

This is my CMakeLists.txt

    set(CPACK_BINARY_DRAGNDROP ON)
    set(CPACK_GENERATOR DragNDrop)
    set(CPACK_PACKAGE_FILE_NAME "My-CPack-App-1.0.0")
    set(CPACK_DMG_VOLUME_NAME "My CPack App")
    set(CPACK_DMG_BACKGROUND_IMAGE "DMGBackground.png")
    set(CPACK_PACKAGE_ICON "VolumeIcon.icns")
    set(CPACK_DMG_DS_STORE_SETUP_SCRIPT "adjust_dmg.scpt")

During build, the custom volume icon is visible, but vanishes after a few moments. It looks like the disk image is rewritten as soon as you have setup_script enabled. Disabling the AppleScript will create the volume icon, but the Finder window will not look as expected.


The CPACK_DMG_DS_STORE variant never worked for me (Icon size not correct, no background image). But if you have a tutorial how to do that, I'm open.


## Build instruction

    cmake . && make && make package
