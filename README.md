# cpp_watchlist
Below are some C++ libraries I find useful. 

- This repository is created for my own reference. 
- I want to keep the list as short as possible. 
- Some items are not C++ libraies themselves, but are important to work with C++ projects, thus also included.

## package manager
[spack](https://github.com/spack/spack). Spack is to C++ what `venv` to Python. 
With spack, different versions of the same C++ library can coexist side by side. 
They can different by release verions, compiler choice, compiling flags, feature switch on/off. The user can painlessly try
out as  many different combinations as he wants. Spack is a must-have if you have to twist C++ libraies a lot.  
[Conan](https://github.com/conan-io/conan). With Conan, one can use binary libraries without much of pain, and fall back to
buiding from source if the binary version of a library is not avalible. Using Conan to install a dependency is somehow like
use `apt` to install the "dev" version of a package on Debian/Ubuntu, but Conan is cross-flatform, is also has more configurable
options, for example, specifying the verion of the library required.
## build tool
[CMake](https://cmake.org/). It does not matter what I think of CMake. It is the de facto building tool used by most C++ libraries. 
Working with C++ requires the programmer knows some CMake. It is important to learn some [Modern CMake](https://cliutils.gitlab.io/modern-cmake/).

## library collections
[folly](https://github.com/facebook/folly). Folly stands for "Facebook Open-source library". It is actually a collection of useful libraries. 
If something is missing from the standard library of C++, one might find it in folly.

## memory allocator 
 [jemalloc](https://github.com/jemalloc/jemalloc), memory allocator from Facebook with better performance with multithreading.
 
## network
- [asio](https://github.com/chriskohlhoff/asio/), asynchronous network programming library, supports serial ports too. It also has SSL support.
- [beast](https://github.com/boostorg/beast), http ans WebSocket library built upon Asio.

## data storage and quering
If you need a in-process database:
- [SQLiteCpp](https://github.com/SRombauts/SQLiteCpp), a C++ wrapper for the [SQLite](https://www.sqlite.org/about.html) library, a in-process SQL databse engine.
- [LebelDB](https://github.com/google/leveldb), a on-disk key-value data egine. 

## testing
[Catch2](https://github.com/catchorg/Catch2), a unit test framework, can either be used as a header-only library (for convenience) or linked as a static library (for better complilation time when the tested project grows bigger). 

## remote procedure call & message queue
- [gRPC](https://github.com/grpc/grpc), a RPC library using [protobuf](https://github.com/protocolbuffers/protobuf) underneath to serializing structured data.
- [ZeroMQ](https://github.com/zeromq/libzmq), publish and subscribe messages over network.

## image processing
[openCV](https://github.com/opencv/opencv), only use its "core", "imgproc" and "imgcodecs" modules.

## linear algebra
[Eigen](https://gitlab.com/libeigen/eigen), template library for linear algebra. It can also linked against IntelMKL, OpenBlas, Lapack, etc.

## string formatting
[fmt](https://github.com/fmtlib/fmt), type-safe alternative for C's `printf`. Goodbye, idiotic `iostream`.

## reduce boilerplate
[boost operator](https://www.boost.org/doc/libs/1_65_0/libs/utility/operators.htm), part of tis functionality can be replaced by the "space operator" introduced in C++20.

## Parse structured text
- [tinyxml2](https://github.com/leethomason/tinyxml2), parse xml data.
- [RapidJSON](https://github.com/Tencent/rapidjson), parse Json data.
- [toml++](https://github.com/marzer/tomlplusplus/), parse TOML file.
- [yaml-cpp](https://github.com/jbeder/yaml-cpp), parse YAML file.

## logging
[spdlog](https://github.com/gabime/spdlog), a configurable logging library.

## interprocess communication
[boost interprocess](https://www.boost.org/doc/libs/1_63_0/doc/html/interprocess.html), shared memory, interprocess synchronization primitives, message queue, mapped file, etc.

## add Python wrapper to C++ library
[pybind11](https://github.com/pybind/pybind11), call C++ code from Python.


## Robotics libraries  
