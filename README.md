# Clangd Setup for Windows cross-compilation
### My personal solution to work with Neovim and Clangd on Windows Malware Development

* Prerequisites:
    - [MinGW](https://www.mingw-w64.org/)
    - [Clangd](https://clangd.llvm.org/)
    - [Neovim](https://neovim.io/)

* Setup of the project:
    - It's as easy as running `cmake -S . -G "Unix Makefiles" -B cmake`
    - Symlink the `cmake/compile_commands.json` file to the root of the project.
    - Then create a `.clangd` file in the root of the project with the following content:
    ```yaml
      CompileFlags:
          CompilationDatabase: "cmake"
    ```
    - Finally, run `mkdir build && cd build && cmake .. && make`

* Run Neovim and start using Clangd with *full* Windows (**mingw-w64**) LSP support!
