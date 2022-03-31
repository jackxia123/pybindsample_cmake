#when you first git clone this project, you can run below commmand

mkdir build

cd build

cmake ..

make -j4

# provide the c++ function which can be called by python in example.cpp


# add some compile command in CMakeLists.txt

#call the function in sample.py which is defined in example.cpp


Building with CMake

For C++ codebases that have an existing CMake-based build system, a Python extension module can be created with just a few lines of code:

cmake_minimum_required(VERSION 3.4...3.18)
project(example LANGUAGES CXX)

add_subdirectory(pybind11)
pybind11_add_module(example example.cpp)

This assumes that the pybind11 repository is located in a subdirectory named pybind11 and that the code is located in a file named example.cpp. The CMake command add_subdirectory will import the pybind11 project which provides the pybind11_add_module function. It will take care of all the details needed to build a Python extension module on any platform.

A working sample project, including a way to invoke CMake from setup.py for PyPI integration, can be found in the [cmake_example] repository.

cmake_example(1,2)

    https://github.com/pybind/cmake_example

Changed in version 2.6: CMake 3.4+ is required.

Further information can be found at CMake helpers.
