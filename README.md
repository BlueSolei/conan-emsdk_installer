[![Download](https://api.bintray.com/packages/bincrafters/public-conan/emsdk_installer%3Abincrafters/images/download.svg) ](https://bintray.com/bincrafters/public-conan/emsdk_installer%3Abincrafters/_latestVersion)
[![Build Status](https://travis-ci.com/bincrafters/conan-emsdk_installer.svg?branch=stable%2F1.39.6)](https://travis-ci.com/bincrafters/conan-emsdk_installer)
[![Build status](https://ci.appveyor.com/api/projects/status/github/bincrafters/conan-emsdk_installer?branch=stable%2F1.39.6&svg=true)](https://ci.appveyor.com/project/bincrafters/conan-emsdk-installer)

[Conan.io](https://conan.io) package recipe for [*emsdk_installer*](https://github.com/kripken/emscripten).

Emscripten is an Open Source LLVM to JavaScript compiler

## For Users: Use this package

### Basic setup

    $ conan install emsdk_installer/2.0.11

### Project setup

If you handle multiple dependencies in your project is better to add a *conanfile.txt*

    [requires]
    emsdk_installer/2.0.11

Complete the installation of requirements for your project running:

    $ mkdir build && cd build && conan install ..

Note: It is recommended that you run conan install from a build directory and not the root of the project directory.  This is because conan generates *conanbuildinfo* files specific to a single build configuration which by default comes from an autodetected default profile located in ~/.conan/profiles/default .  If you pass different build configuration options to conan install, it will generate different *conanbuildinfo* files.  Thus, they should not be added to the root of the project, nor committed to git.

## For Packagers: Publish this Package

## Build and package

The following command both runs all the steps of the conan file, and publishes the package to the local system cache.  This includes downloading dependencies from "build_requires" and "requires" , and then running the build() method.

    $ conan create . emsdk_installer/2.0.11@

## Add Remote

    $ conan remote add artifactory https://artifactory01.engit.synamedia.com/artifactory/api/conan/vge-conan-snapshots-local

## Upload

    $ conan upload emsdk_installer/2.0.11 --all -r artifactory

## **Update to latest em-sdk version**

1. find the latest emsdk release at https://github.com/emscripten-core/emsdk/releases
2. add a new entry to `conandata.yml` with the new version's url and sha256 hash
3. build & publish to Synamedia's Artifactory as described in the [Build and Package](#build-and-package)
4. if all well, commit your changes to the master with commit message of pattern 'v\<version\>' (e.g. v2.0.42)

## Conan Recipe License

NOTE: The conan recipe license applies only to the files of this recipe, which can be used to build and package emsdk_installer.
It does *not* in any way apply or is related to the actual software being packaged.

[MIT](git@github.com:bincrafters/conan-emsdk_installer.git/blob/master/LICENSE.md)
