# OSQP-Wrapper
Simple C++ wrapper for [OSQP](http://osqp.readthedocs.io/en/latest/index.html) library.

## Dependeces
- [OSQP](http://osqp.readthedocs.io/en/latest/index.html) of course :smile:;
- [Eigen3](http://eigen.tuxfamily.org/index.php?title=Main_Page);
- [cmake](https://cmake.org/);
- [googletest](https://github.com/google/googletest) for testing.  

**Notice**: if you want to use this Wrapper please use [this](https://github.com/traversaro/osqp/tree/add_cmake_install) version of the OSQP library.

## Build the library and the application
### Linux/macOs
```sh
git clone https://github.com/GiulioRomualdi/OSQP-Wrapper.git
cd OSQP-Wrapper
mkdir build && cd build
cmake ../
make
[sudo] make install
```
If you want to enable tests set the `BUILD_TESTING` option to `ON`.

**Notice**: ``sudo`` is not necessary if you specify the ``CMAKE_INSTALL_PREFIX``. In this case it is necessary to add in the ``.bashrc`` the following lines:

### Linux
```
export OSQP_Wrapper_DIR=/path/where/you/installed/
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$OSQP_Wrapper_DIR/lib
```

### macOs
```
export OSQP_Wrapper_DIR=/path/where/you/installed/
export DYLD_LIBRARY_PATH=$LD_LIBRARY_PATH:$OSQP_Wrapper_DIR/lib
```

## How to use the wrapper
[Here](./example/) you can find a simple example that shows how to use this library.  
If you have installed the `OSQP-Wrapper` in a custom directory `find_package(OSQPWrapper)` will fail. To solve this issue
please add the following command to your `CMakeLists.txt` file
```cmake
list(APPEND CMAKE_PREFIX_PATH $ENV{OSQP_Wrapper_DIR})
```

## API
[Here](https://giulioromualdi.github.io/OSQP-Wrapper/) you can find the documentation.

## Bug reports and support
All types of [issues](https://github.com/GiulioRomualdi/OSQP-Wrapper/issues/new) are welcome :smile:. 
