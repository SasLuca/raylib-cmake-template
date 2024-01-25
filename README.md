# Simple and portable CMake template for raylib

This is a basic project template for raylib using CMake and has been tested with Visual Studio, Visual Studio Code and CLion.

The master branch of the raylib source code is downloaded using CMake FetchContent from github and compiled from source as it is much easier than including prebuilt binaries for every platform and configuration.

Building from the cmake file will build both raylib and `src/main.c` which includes a basic example of a raylib program.

## Asset handling

The example in `src/main.c` uses an example image located in the `assets` folder.
To load it we use `ASSETS_PATH`, which is a string macro with the *absolute* path "assets" directory.
This macro is defined in the `CMakeLists.txt` file on line `23`.
 
If you plan on releasing or sharing your game consider manually setting the value of the `ASSETS_PATH` macro.

In C you can concatenate string literals by putting them next to each other, 
eg: `"A" "B"` is `"AB"`. So ASSETS_PATH `"test.png"` becomes `"/path/to/your/assets/test.png"`

If you wanna share your game with others you should set ASSETS_PATH to be a *relative* path like "./assets/". You can do this in the CMakeLists.txt file. 

## Using C++

Using c++ is quite simple, just change these lines in the `CMakeLists.txt`
from
```
project(my_raylib_game C)

set(CMAKE_C_STANDARD 99)

file(GLOB_RECURSE PROJECT_SOURCES CONFIGURE_DEPENDS "${CMAKE_CURRENT_LIST_DIR}/sources/*.c")
```
to
```
project(my_raylib_game CXX)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

file(GLOB_RECURSE PROJECT_SOURCES CONFIGURE_DEPENDS "${CMAKE_CURRENT_LIST_DIR}/sources/*.cpp")
```
After this just reload cmake and it should build fine.
