[![wakatime](https://wakatime.com/badge/user/17eacdf5-0954-4233-89e5-cf09a2e230eb/project/f493991c-890e-48ab-9625-4bdd1e9e68c7.svg)](https://wakatime.com/badge/user/17eacdf5-0954-4233-89e5-cf09a2e230eb/project/f493991c-890e-48ab-9625-4bdd1e9e68c7)

# Cpp20_Ultimate_Repo_Template_2025
The Ultimate Hello World - Application/Library Project Template For C++20
Contains scripts and build systems to build with virtually any Compiler on any IDE, Code Editor, or Terminal






## Multiplatform Build System
Including CMake, vscode, msvc, builds.





### On Windows






#### With MSVC - Microsoft Visual C/C++ Studio 2022 Community

Project.sln - Solution File in the Main Directory



#### With VSCode
tasks.json




### On Linux




#### With VSCode or VSCodium
Uses a CMake Build system you can run tasks.json task, or build buttons at the bottom of the CMake Extension
Or better yet Build And Run From Command-Line Terminal below!




#### Built-in Fully Autonomous Build Scripts - Install VulkanSDK, Dependencies, and Compile Directly from Commandline in Linux Terminal
you will need to chmod -x the following to use:
./VulkanSDK/install_vulkansdk_debian.sh
./VulkanSDK/uninstall_vulkansdk_debian.sh - to uninstall obviously

./build.sh gcc Release
./install.sh gcc Release
./run.sh

or:

./build.sh clang Debug
./install.sh clang Debug


Notice: the difference in compiler in the Debug builds, clang vs gcc which ever compiler you prefer to use.
