# Starter C++17 - VS Code

## Getting started

Add your `...\mingw64\bin` to your path.  I use MSYS2's mingw64 tools, so it's `C:\msys64\mingw64\bin`. That's it, use it if you want.  I'm gonna keep this small because I don't like having to re-read the initial setup and configuration notes on VS Code docs every time I need a tiny C++ project with build/debug/syntax stuff ready to go.

## `.vscode\c_cpp_properties.json`

```json
{
    "configurations": [
        {
            "name": "Win32",
            "includePath": [
                "${workspaceFolder}/**"
            ],
            "defines": [
                "_DEBUG",
                "UNICODE",
                "_UNICODE"
            ],
            "windowsSdkVersion": "10.0.18362.0",
            "compilerPath": "C:\\msys64\\mingw64\\bin\\g++.exe",
            "cStandard": "c11",
            "cppStandard": "c++17",
            "intelliSenseMode": "gcc-x64"
        }
    ],
    "version": 4
}
```

## `.vscode\tasks.json`

```json
{
    "version": "2.0.0",
    "tasks": [
        {
            "label": "YOUR LABEL HERE",
            "type": "shell",
            "command": "g++",
            "args": [
                "-g",
                "-std=c++17",
                "main.cpp",
                "-o",
                "YOUR_COMPILED_CPP_PROGRAM",
            ],
            "group": {
                "kind": "build",
                "isDefault": true
            },
        },
    ]
}

```


## `.vscode\launch.json`

```json
{
    "version": "0.2.0",
    "configurations": [
        {
            "name": "(gdb) Launch",
            "type": "cppdbg",
            "request": "launch",
            "program": "${workspaceFolder}/YOUR_COMPILED_CPP_PROGRAM.exe",
            "args": [],
            "stopAtEntry": true,
            "cwd": "${workspaceFolder}",
            "environment": [],
            "externalConsole": true,
            "MIMode": "gdb",
            "miDebuggerPath": "C:\\msys64\\mingw64\\bin\\gdb.exe",
            "setupCommands": [
                {
                    "description": "Enable pretty-printing for gdb",
                    "text": "-enable-pretty-printing",
                    "ignoreFailures": true
                }
            ]
        }
    ]
}

```

