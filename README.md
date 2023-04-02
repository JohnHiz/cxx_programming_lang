# C++ Programming Language

This repository contains information about the practical part of the "C++ Programming" book.

## Prerequisites

### Required packages

On Archlinux:
```bash
sudo pacman -Syu --needed base-devel git cmake ninja
```

On Ubuntu:
```bash
sudo apt install build-essential git cmake ninja-build
```

On MacOS:
```bash
xcode-select --install
brew install git cmake ninja
```

## Downloading

```bash
git clone https://github.com/JohnHiz/cxx_programming_lang.git
```

## Configuration

```bash
cd cxx_programming_lang
CMAKE_CONFIG=Release
BUILD_DIR=build
cmake -S . -B ${BUILD_DIR} -DCMAKE_BUILD_TYPE=${CMAKE_CONFIG}
```

Optionally add `-DCMAKE_VERBOSE_MAKEFILE:BOOL=ON` to see the compile commands.
Also optionally, add `-GNinja` to the cmake arguments (this is what I am developing with).
Other build types are: `RelWithDebug`, `RelWithDebInfo`, `Debug` and `BetaTest`.
See [stackoverflow](https://stackoverflow.com/a/59314670/1487069) for an explanation
of the different types.

## Building

```bash
NUMBER_OF_CPUS=$((`nproc` - 2))                                            # Linux
NUMBER_OF_CPUS=$(expr $(sysctl -n hw.ncpu) - 2)                          # MacOS

cmake --build ${BUILD_DIR} --config ${CMAKE_CONFIG} --parallel ${NUMBER_OF_CPUS}
```

Just set `NUMBER_OF_CPUS` to whatever you want, of course.
