# Cmake
Examples of projects with CMake.

<h1>Introduction</h1>

CMake is:
* cross-platform
* free 
* open-source
* compiler-independent

<h2>Compilation with gcc</h2>

When your project contains just two files (main.c code.c), you can easily compily it from the terminal using following commands:

```bash
gcc -Wall -Wextra -Werror -std=c99 -pedantic -g -o exe code.c main.c
```

You have now an executable that you can run, called <i>exe</i>.

<h2>Using Makefiles for compilation</h2>

When working with many files, it becomes nearly impossible to use command line commands for compilation.
Instead you can use configuration files in which you specify which files and with which flags you want to compile.

```bash
CC=gcc
CFLAGS=-I.
DEPS = code.h

%.o: %.c $(DEPS)
	$(CC) -c -o $@ $< $(CFLAGS)

project: main.o code.o 
	$(CC) -o exe main.o code.o 
```

<h2>Using CMake for compilation</h2>

Build systems like <i>Make</i> are usualy platform specific.
You can however use a meta build system like CMake which is platform independent.

```bash
mkdir build
cd build
cmake..
cmake --build .
```

<h2>Make vs CMake</h2>

Make is a build system.
CMake is a build system generator.
You can use CMake to generate Makefiles, but it can also work with Ninja, KDEvelop and Xcode projects, as well as Visual Studio solutions

<h1>Requirements</h1>
 
In order to run our examples you need the following:

* CMake v3.15+
* gcc
* make
 
</h1>Table of contents</h1>
