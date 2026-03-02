# A C++-20 modules example

I've taken one of the classes from sebsjames/maths and tried to compile it as a module.

`sm::range` is normally `#included` as a header file. Here, I've turned it into a module, and made a simple demo program called use_range.cpp.

Building this project requires at least cmake 3.28.5* and gcc 14 or clang
18. It also requires the ninja build system (version 1.11.1 works).

* See [this discussion with Ben Boeckel from Kitware](https://discourse.cmake.org/t/how-can-i-be-sure-that-a-c-20-module-is-not-re-compiled-after-a-non-module-code-change/15535/8). Annoyingly, this is just a tiny bit newer than the cmake packaged on the current long term support release of Ubuntu (24.04), so building on that platform requires installation of an updated cmake.

```bash
mkdir build
cd build
cmake .. -GNinja
# make all verbose
cmake --build . --target all --verbose
```

```bash
# to clean:
cmake --build . --target clean

# One target non-verbose:
cmake --build . --target use_range

# Two targets, verbose:
cmake --build . --target use_range use_range2 --verbose

# Using ninja directly
ninja -d explain --verbose # instead of cmake --build . --target all
```
