# SpritRunner
SpiritRunner is a simple browser platform game developed in WebAssembly.

## How to install an environment
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

## Compile and run
In `SpiritRunner` directory type
```
emcc hello.c -s WASM=1 -o hello.html
emrun --port 8080 hello.html
```
and enjoy.