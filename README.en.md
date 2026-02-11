# MSYS2 + VS Code C++ Setup Guide

This document explains how to install MSYS2 on Windows, create a `main.cpp`, and open it in VS Code.

## 1) Prerequisites

- Download MSYS2: [https://www.msys2.org/](https://www.msys2.org/)
- Install VS Code: [https://code.visualstudio.com/](https://code.visualstudio.com/)

## 2) Install and update MSYS2

1. Run the MSYS2 installer and use the default path.
2. Launch the "MSYS2 UCRT64" terminal.
3. Update packages.

```bash
pacman -Syu
```

If the terminal closes after updates, reopen "MSYS2 UCRT64" and run it once more.

```bash
pacman -Syu
```

## 3) Install the C++ compiler

Install GCC for the UCRT64 environment.

```bash
pacman -S --needed base-devel mingw-w64-ucrt-x86_64-gcc
```

Verify:

```bash
g++ --version
```

## 4) Create a working folder

Example folder: `C:\Users\user\Desktop\CHJ\helloGroup\cpp`

```bash
mkdir -p /c/Users/user/Desktop/CHJ/helloGroup/cpp
cd /c/Users/user/Desktop/CHJ/helloGroup/cpp
```

## 5) Create main.cpp

Create the file with the following contents.

```bash
cat > main.cpp << 'EOF'
#include <iostream>

int main() {
    std::cout << "Hello, MSYS2 + VS Code!" << std::endl;
    return 0;
}
EOF
```

## 6) Open in VS Code

From the MSYS2 UCRT64 terminal:

```bash
code .
```

Open `main.cpp` in the editor.

## 7) Build and run (optional)

```bash
g++ main.cpp -o main.exe
./main.exe
```

## 8) Troubleshooting checklist

- `g++` not found: make sure you are using the UCRT64 terminal
- `code` not found: ensure VS Code is on PATH
- Build errors: confirm the current directory and file name

---
