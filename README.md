# Project README

## Overview
This project is a simple simulation of balls and lines, where balls interact with each other according to physical laws. It supports multiple platforms including Linux, Windows, WebAssembly, and Wine.

## Features
- Simulation of bouncing balls.
- Lines that can be drawn and used as boundaries or paths for the balls.
- Basic physics engine to handle collisions and movement.

## Project Structure
```
Gui_Balls_Lines_Physics/
├── build/              # .exe files produced by Main.c
├── bin/                # .so / .dll produced by *.c in libs
├── libs/               # *.c for bin
├── lib/                # librarys for my own languages
├── code/               # scripts from my custom languages for example .rex, .ll, .omml
├── data/               # Datafile for example .txt or dumped files
├── assets/             # images and sound files
├── src/                # source code
│   ├── Main.c          # Entry point
│   └── *.h             # stand alone Header-based C-files, without *.c files that implement it
├── Makefile.linux      # Linux Build configuration
├── Makefile.windows    # Windows Build configuration
├── Makefile.wine       # Wine Build configuration
├── Makefile.web        # Emscripten Build configuration
└── README.md           # This file
└── LICENCE
└── .gitignore
```

### Prerequisites
- C/C++ Compiler and Debugger (GCC, Clang)
- Make utility
- Standard development tools
- Libraries needed in specific projects:
  - Linux: X11
  - Windows: WINAPI, user32, gdi32, winmm
  - WebAssembly: Emscripten

## Build & Run
### Building
To build the project for a specific platform, navigate to the project directory and run:

- **Linux**:
  ```sh
  make -f Makefile.linux all
  ```

- **Windows**:
  ```sh
  make -f Makefile.windows all
  ```

- **Wine (Cross-compilation for Windows)**:
  ```sh
  make -f Makefile.wine all
  ```

- **WebAssembly**:
  ```sh
  make -f Makefile.web all
  ```

### Execution
To run the executable, use:

- **Linux**:
  ```sh
  make -f Makefile.linux exe
  ```

- **Windows**:
  ```sh
  make -f Makefile.windows exe
  ```

- **Wine (Cross-compilation for Windows)**:
  ```sh
  make -f Makefile.wine exe
  ```

- **WebAssembly**:
  ```sh
  emrun --no_browser --port 8080 build/
  ```
  Open a web browser and navigate to `http://localhost:8080` to view the simulation.

### Cleaning
To clean the build artifacts, use:

```sh
make -f Makefile.linux clean
```

For all platforms:
```sh
make -f Makefile.allclean
```

This README provides a clear guide on how to build and run the project for different target platforms.