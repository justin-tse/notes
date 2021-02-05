2021.02.05
I want to install [style50](https://cs50.readthedocs.io/style50/)
So I need to Install Artistic Style 3.0.
And I follow the instruction in Mac for Xcode
>INSTALL
Only the astyle executable is installed. The library project installs are sent to UninstalledProjects in the Build directory. The following instructions are for the astyle executable and documentation files. The default install directory is /usr/bin for the executable and /usr/share/doc/astyle for the documentation. You must have the appropriate permissions to use install. If sudo is not used for the install, an error will occur during the build.

>To install the astyle executable in the default directory:

>cd astyle/build/xcode
sudo xcodebuild install -project AStyle.xcodeproj
A script is used to install the documentation from the same directory.

>sudo bash install.sh

```bash

CreateUniversalBinary /usr/bin/astyle normal arm64\ x86_64 (in target 'AStyle' from project 'AStyle')
    cd /Users/XF/Downloads/astyle/build/xcode
    /Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/bin/lipo -create /Users/XF/Downloads/astyle/build/xcode/Build/Intermediates/AStyle.build/Release/AStyle.build/Objects-normal/arm64/Binary/astyle /Users/XF/Downloads/astyle/build/xcode/Build/Intermediates/AStyle.build/Release/AStyle.build/Objects-normal/x86_64/Binary/astyle -output /usr/bin/astyle
fatal error: /Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/bin/lipo: can't create temporary output file: /usr/bin/astyle.lipo (Operation not permitted)
Command CreateUniversalBinary failed with a nonzero exit code

** INSTALL FAILED **


The following build commands failed:
        CreateUniversalBinary /usr/bin/astyle normal arm64\ x86_64
```
```bash
(base)  ✘ XF@MacBook-Pro ⮀ ~/Downloads/astyle/build/xcode ⮀ sudo bash install.sh

Password:

Installing documentation to /usr/share/doc/astyle
install: mkdir /usr/share/doc/astyle: Operation not permitted
Error 71 returned from function
Did you use 'sudo'?

** INSTALL FAILED **
```

- But I have uninstalled
```bash
(base)  ✘ XF@MacBook-Pro ⮀ ~/Downloads/astyle/build/xcode ⮀ sudo bash uninstall.sh


Unnstalling astyle from /usr/bin
Unnstalling documentation from /usr/share/doc/astyle

** INSTALL SUCCEEDED **
```