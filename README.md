# TWRP for Tolino eInk reader devices
### State
TWRP builds and is fully functional (hopefully).

### Known working devices
- Tolino Page
- Tolino Shine 2 HD
- Tolino Vision 4 HD

### Test without installation
1) enter fastboot;
2) in cmd do `fastboot boot <path_to_recovery_image>`

### Installation
1) enter fastboot;
2) in cmd do `fastboot flash recovery <path_to_recovery_image>`

### How to enter recovery
1) connect your device to pc;
2) completely turn off device;
3) press and hold glowlight button;
4) turn device on (while still holding glowlight button);

### How to enter fastboot
1) connect your device to pc;
2) completely turn off device;
3) press and hold glowlight button;
4) press and hold power button;
5) wait while device turns on while holding both buttons;

### How to build TWRP
1. `repo init --depth=1 -u git://github.com/minimal-manifest-twrp/platform_manifest_twrp_omni.git -b twrp-5.1`
2. `repo sync -n -j 1 && repo sync -l -j 4`
3. `clone this repo to <twrp_repo>/device/TOLINO/ntx_6sl`
4. apply patches from <twrp_repo>/device/TOLINO/ntx_6sl/patches directory
5. open terminal in <twrp_repo> directory;
6. `. build/envsetup.sh`
7. `add_lunch_combo omni_ntx_6sl-userdebug`
8. `lunch omni_ntx_6sl-userdebug`
9. `mka recoveryimage`

if everything is successful you should find built recovery by path <twrp_repo>/out/target/product/ntx_6sl/recovery.img
