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


## 20210210  brew update error
- Problem
```bash
(base)  ✘ XF@MacBook-Pro ⮀ ~/src/justin-tse/notes/edX/cs50t ⮀ ⭠ main± ⮀ brew update
Error: 
  homebrew-core is a shallow clone.
  homebrew-cask is a shallow clone.
To `brew update`, first run:
  git -C /usr/local/Homebrew/Library/Taps/homebrew/homebrew-core fetch --unshallow
  git -C /usr/local/Homebrew/Library/Taps/homebrew/homebrew-cask fetch --unshallow
This restriction has been made on GitHub's request because updating shallow
clones is an extremely expensive operation due to the tree layout and traffic of
Homebrew/homebrew-core and Homebrew/homebrew-cask. We don't do this for you
automatically to avoid repeatedly performing an expensive unshallow operation in
CI systems (which should instead be fixed to not use shallow clones). Sorry for
the inconvenience!
```
- Solution

```bash
(base)  ✘ XF@MacBook-Pro ⮀ ~/src/justin-tse/notes/edX/cs50t ⮀ ⭠ main± ⮀ git -C /usr/local/Homebrew/Library/Taps/homebrew/homebrew-core fetch --unshallow
remote: Enumerating objects: 359301, done.
remote: Counting objects: 100% (359280/359280), done.
remote: Compressing objects: 100% (145246/145246), done.
remote: Total 350789 (delta 208113), reused 345248 (delta 202741), pack-reused 0
Receiving objects: 100% (350789/350789), 94.61 MiB | 57.00 KiB/s, done.
Resolving deltas: 100% (208113/208113), completed with 7864 local objects.
From https://github.com/Homebrew/homebrew-core
   c1b738be8f..0e1ceaf36e  master     -> origin/master
(base)  XF@MacBook-Pro ⮀ ~/src/justin-tse/notes/edX/cs50t ⮀ ⭠ main± ⮀ git -C /usr/local/Homebrew/Library/Taps/homebrew/homebrew-cask fetch --unshallow
remote: Enumerating objects: 54072, done.
remote: Counting objects: 100% (51588/51588), done.
remote: Compressing objects: 100% (15813/15813), done.
remote: Total 45634 (delta 33305), reused 42067 (delta 29805), pack-reused 0
Receiving objects: 100% (45634/45634), 19.19 MiB | 31.00 KiB/s, done.
Resolving deltas: 100% (33305/33305), completed with 3453 local objects.
From https://github.com/Homebrew/homebrew-cask
   d66341771c..332906e385  master     -> origin/master
```