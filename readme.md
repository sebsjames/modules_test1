# A C++-20 modules example

I've taken one of the classes from sebsjames/maths and tried to compile it as a module.

`sm::range` is normally `#included` as a header file. Here, I've turned it into a module, and made a simple demo program called use_range.cpp.

Building this project requires cmake 3.28 or above and the ninja build system.

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
