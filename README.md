ProjectTemplate
===============

A [cmake](https://cmake.org),
[ninja](https://github.com/ninja-build/ninja), and
[googletest](https://github.com/google/googletest)-based C++ project template.


Prerequisites
-------------

To build, you'll need [cmake](https://cmake.org),
[ninja](https://github.com/ninja-build/ninja), and a clang build toolchain
installed on your system.


Obtaining the source
--------------------

First, clone the repo. Then, initialise and fetch git submodules:

    # Initialise local configuration file.
    git submodule init

    # Fetch submodules (googletest).
    git submodule update


Updating git submodules
-----------------------

To update the git submodules to a newer commit, simply run:

    git submodule update --remote


Building and running
--------------------

First, generate the ninja build files:

    # For debug build:
    cmake -DCMAKE_BUILD_TYPE=Debug -GNinja

    # For release build:
    cmake -DCMAKE_BUILD_TYPE=Release -GNinja


### Unit tests

To build and run the unit tests, run:

    ninja
    ./bin/libfoo_tests


### Executable binary

To build and run the binary:

    ninja
    ./bin/main
