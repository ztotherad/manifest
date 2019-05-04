# PR-OS


 - PR-OS is a small project I am working on out of bordem and the desire to learn.

 - The goal of PR-OS is to maintain a pure experience:

   + All custom settings are integrated as cleanly as possible into the Settings app.

   + Absolutely __no__ branding of PR-OS anywhere throughout the ROM.

   + No options to change major UI components. For example, options to change the lockscreen clock. The UI is what makes a ROM itself, so why should you be able to change it?

 - Final note. Pull requests are welcomed! Just please be sure to maintain authorship out of respect for other developers work.

## Building


### Required Packages


   **Arch Linux**

   Install the `aosp-devel` metapackage from the Arch User Repository.



   **Ubuntu**

   Follow [Google's guide](https://source.android.com/setup/build/initializing) to see the packages required to build AOSP.



   **Fedora**

   Follow [Fedora's guide](https://fedoraproject.org/wiki/HOWTO_Setup_Android_Development#Compiling_Android_from_Source) to see the packages required to build AOSP.


### Cloning trees
This step varies __vastly__ per device. For PR-OS, vendor/pr/config/common_full_phone.mk will need to be included in your device tree if you're building for a device with cellular capabilites. Otherwise, include vendor/pr/config/common.mk.


At the top of vendor/pr/build/tasks/kernel.mk are flags and descriptions for inline kernel building.


### Starting the build
This step can vary from 10 minutes to 12 hours depending on how powerful your PC is. You will need __at least__ 8 gigabytes of RAM, 250 gigabytes of storage, a quad core processor, and patience.


To initiate the build, first source the enviroment setup script in build/envsetup.sh.
```
. build/envsetup.sh
```
Then to start the build, use the `build` command.
```
build -d sailfish
```
Enter the command `build --help` to see the available parameters.


Now Android is building. Again, this will take a while.


### Finding the build
If your Android build completed without any errors, congratulations. The ZIP file of the build will be located in `out/target/product/<device codename>`. The filename will begin with PR-OS.
