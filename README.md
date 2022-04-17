# C++ Tools and Libraries
Below are some C++ tools and libraries I find useful. 

- This repository is created for my own reference. 
- I want to keep the list as short as possible. 
- I have not tried all of them.

## package manager
1. [spack](https://github.com/spack/spack). Spack is to C++ what `venv` to Python. 
With spack, different versions of the same C++ library can coexist side by side. 
They can different by release verions, compiler choice, compiling flags, features switch on/off. The user can painlessly try
out as  many different combinations as he wants. Spack is a must-have if you have to twist C++ libraies a lot and often have
multiple incompatible versions of the same libraries around. It could also be very useful to those who need to deploy  many
binaries with constant updating of dependencies. 
2. [Conan](https://github.com/conan-io/conan). With Conan, one can use binary libraries without much of pain, and fall back to
buiding from source if a certain version of a library is not avalible. Using Conan to install a library is somehow like
using `apt` to install the "dev" version of a package on Debian/Ubuntu. The difference is that Conan is cross-flatform, and also with
more configurable options, for example, specifying the verion of a library. More importantly, Conan does not mess with system-wide
libraries. It is never a good idea to use a system package manager to manage project dependencies for this reason. 
## build tool
1. [CMake](https://cmake.org/). CMake is horrible. I wish I could avoid it.
But It has become the de facto building tool used by most C++ libraries because of momentum.
No matter what a C++ programmer might think of CMake, he usually need to know some CMake to do his work.
If you have to use CMake, it is important to learn some [Modern CMake](https://cliutils.gitlab.io/modern-cmake/).
2. [Make](https://www.gnu.org/software/make/). Make is even older than CMake, and is often used as the backend for CMake. For small C/C++
projects, simple Makefiles is sufficient to build them. It is important to know the basics of Make.
3. [Ninja](https://github.com/ninja-build/ninja). Ninja is like `make`, but has a smaller scope. It is supposed to be used as a backend
by a building system working at a higher level. Since `ninja` files are not supposed to be manually written, the DSL used by `ninja` is designed for
maximal speed. 
4. [Bazel](https://github.com/bazelbuild/bazel), Bazel is designed to work with multiple langauges and build things at scale. When you have a very large codebase
that consists of source code written in multiple programming langauges, to ensure the correctness of building becomes important. Also for very large codebase,
[remote caching](https://github.com/buchgr/bazel-remote/) of binary artifacts becomes necessary. Bazel can do this because it uses a server-client archetecture,
designed while having scalability in mind. Bazel is best suited for monorepo development. 

## library collections
1. [folly](https://github.com/facebook/folly). Folly stands for "Facebook Open-source library". It is actually a collection of useful libraries. 
If something is missing from the standard library of C++, one might find it in folly.
2. [abseil-cpp](https://github.com/abseil/abseil-cpp). Abseil-cpp is a collection of C++11 compliant libraries from Google. Many types included in
it have replacements in newer versions of C++, while others are designed with different design priorities. For example, `absl::Time` and `absl::Duration` are
designed to replace `std::chrono::time_point` and `std::chrono::duration` in common tasks. They have less capabilites and guarantees but they also don't have
to use the template-heavy appraoch that the standard library uses.
3. [Poco](https://github.com/pocoproject/poco). Poco is a collection of C++ libraries that are designed for ease of use. 
It focuses on network-centric applications.
4. [Boost](https://github.com/boostorg/boost). A collect of libraries that aim to supplement the standard library.

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
