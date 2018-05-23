LLVM 6.0 + Ollvm + Armariris
================================

This directory and its subdirectories contain source code for LLVM,
a toolkit for the construction of highly optimized compilers,
optimizers, and runtime environments.

LLVM is open source software. You may freely distribute it under the terms of
the license agreement found in LICENSE.txt.

Please see the documentation provided in docs/ for further
assistance with LLVM, and in particular docs/GettingStarted.rst for getting
started with LLVM and docs/README.txt for an overview of LLVM's
documentation setup.

If you are writing a package for LLVM, see docs/Packaging.rst for our
suggestions.

How to Build:

  $ git clone https://github.com/yazhiwang/ollvm-tll.git
  $ mkdir build
  $ cd build
  $ cmake -DCMAKE_BUILD_TYPE=Release ../ollvm-tll/
  $ make -j7
  
  
  use -mllvm -bcf -mllvm -fla -mllvm -sub -mllvm -sobf
  
* Instructions Substitution -mllvm -sub
* Bogus Control Flow -mllvm -bcf
* Control Flow Flattening -mllvm -fla
* String Obfuscation -mllvm -sobf


It has been tested on Android 3.2 preview and NDKr17:
To use it on Android studio, you need to goto following folder:
$(NDK_FOLDER)/toolchains/
cp -rf llvm orig_llvm
cd llvm/prebuilt/darwin-x86_64 # it depends on your OS, darwin-x86_64 can be others
rm -rf *
cp -rf ($BUILD_OLLVM)/bin .
cp -rf ($BUILD_OLLVM)/lib .


# This code repo is similar to the previous work of Qrilee:
https://github.com/Qrilee/Obfuscator-LLVM
The reason why I redo it is because from NDKr17, it will use clang 6.0. And by default there is parameter "-nostdlib++", which is not supported by the LLVM version he did. There are several hassles when trying to use OLLVM on Android studio. Above steps are the easiest way to compile your NDK project with obfuscation using OLLVM+String OBFU
