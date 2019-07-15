# SpritRunner
SpiritRunner is a simple browser platform game developed in WebAssembly.

## Dependencies

* C++14
* CMake >= 3.1
* SDL 2
* Corrade
* Magnum Engine
* Emscripten

## Pipeline

- Install Emscripten properly
- Build Corrade with cross-compilation for Emscripten
- Build Magnum with cross-compilation for Emscripten
- Build SpiritRunner with cross-compilation for Emscripten

## How to install an environment

https://doc.magnum.graphics/corrade/building-corrade.html#building-corrade-cross-emscripten
https://doc.magnum.graphics/magnum/building.html#building-cross-emscripten
https://doc.magnum.graphics/magnum/classMagnum_1_1Platform_1_1EmscriptenApplication.html


* `Emscripten`
```
git clone https://github.com/emscripten-core/emsdk.git
cd emsdk
./emsdk install latest
./emsdk activate latest
```
To be able to use emscripten tools type 
```
source ./emsdk_env.sh --build=Release
```
or place it in your `~/.bashrc`

* `Magnum`
```
git clone git://github.com/mosra/magnum.git
mkdir build && cd build
cmake .. \
    -DCMAKE_INSTALL_PREFIX=/usr \
    -DWITH_SDL2APPLICATION=ON
make
make install # sudo may be needed
```

## Compile and run
In `SpiritRunner` directory type
```
mkdir build-emscripten && cd build-emscripten
cmake .. \
    -DCMAKE_TOOLCHAIN_FILE="../toolchains/generic/Emscripten.cmake" \
    -DCMAKE_PREFIX_PATH=/usr/lib/emscripten/system \
    -DCMAKE_INSTALL_PREFIX=/srv/http/emscripten
cmake --build .
cmake --build . --target install
```
and enjoy.