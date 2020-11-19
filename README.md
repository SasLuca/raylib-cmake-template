# Simple and portable CMake template for raylib

This is a very basic project template for raylib using CMake and has been tested with Visual Studio, Visual Studio Code and CLion.

The raylib source code is included in the libs folder as it is much easier than including prebuilt binaries for every platform and configuration.

Building from the cmake file will build both raylib and `src/main.c` which includes a basic example of a raylib program.

The example in `src/main.c` uses an example image located in the `assets` folder.

The absolute path to the assets folder is defined by a macro `ASSETS_PATH` in the CMake file automatically which is useful during development. If you plan on releasing or sharing your game consider manually setting the value of the `ASSETS_PATH` macro.

## How to use with C++
To use with C++ simply rename `main.c` to `main.cpp` and then change the following lines in CMakelists.txt:

From:
```
project(raylib_template C)

set(CMAKE_C_STANDARD 99)

add_executable(raylib_template src/main.c)
```

To:
```
project(raylib_template CXX)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_executable(raylib_template src/main.cpp)
```
