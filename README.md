# Duke: a minimal JavaScript interpreter

Duke is a minimal JavaScript interpreter, which has been build with [Duktape] &ndash; an embeddable and portable Javascript engine with a compact footprint. The `duke` interpreter consumes a single line of JavaScript code and then executes it (while it's possible to run an entire script by minifying it).

## Prerequisites

```sh
pacman --query --info gcc
```
```
Name            : gcc
Version         : 8.3.0-1
Description     : The GNU Compiler Collection - C and C++ frontends
Architecture    : x86_64
URL             : http://gcc.gnu.org
Licenses        : GPL  LGPL  FDL  custom
```

```sh
pacman --query --info make
```
```
Name            : make
Version         : 4.2.1-3
Description     : GNU make utility to maintain groups of programs
Architecture    : x86_64
URL             : http://www.gnu.org/software/make
Licenses        : GPL3
```

```sh
pacman --query --info duktape
```
```
Name            : duktape
Version         : 2.3.0-2
Description     : Embeddable Javascript engine
Architecture    : x86_64
URL             : https://duktape.org/
Licenses        : MIT
```

## Installation

```
npm install
```

## Building

### Clean

```
npm run clean
```

### Make

```sh
npm run build
```

## Execution

### Doing Arithmetic

```sh
echo "1/0" | npm run execute
```
```
⪡ Infinity
```

### Using Functions

```sh
echo "function id(a) { return a; }; id(1)" | npm run execute
```
```
⪡ 1
```

### Simple Logging

```sh
echo "log('message')" | npm run execute
```
```
⪢ message
```
```
⪡ undefined
```

### Throwing Errors

```sh
echo "throw new Error('message')" | npm run execute
```
```
⫷ Error: message
```

### Running Scripts

```sh
cat ./src/duke.js | npm run execute ## or:
```
```sh
npm run execute < ./src/duke.js
```
```
> duke@1.0.0 execute ~
> npx terser | ./dist/Release/GNU-Linux/duke
```
```
 ⪢ Duke: dracula
```
```
 ⪡ undefined
```

[Duktape]: https://duktape.org/

## Copyright

 © 2019 [Hasan Karahan](https://github.com/hsk81)
