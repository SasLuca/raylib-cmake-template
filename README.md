# Simple and portable CMake template for raylib

This is a very basic project template for raylib using CMake and has been tested with Visual Studio, Visual Studio Code and CLion.

The raylib source code is included in the libs folder as it is much easier than including prebuilt binaries for every platform and configuration.

Building from the cmake file will build both raylib and `src/main.c` which includes a basic example of a raylib program.

The example in `src/main.c` uses an example image located in the `assets` folder.

The absolute path to the assets folder is defined by a macro `ASSETS_PATH` in the CMake file automatically which is useful during development. If you plan on releasing or sharing your game consider manually setting the value of the `ASSETS_PATH` macro.