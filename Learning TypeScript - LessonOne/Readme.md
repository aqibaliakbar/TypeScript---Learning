# TypeScript Documentation - Lesson 1

## Introduction

Welcome to the documentation for your TypeScript learning journey! This guide will walk you through the basics of TypeScript installation, configuration, and compiling your TypeScript code into JavaScript.

## Installation

First, ensure you have Node.js and npm installed on your system. Then, install TypeScript globally using npm:

```bash
npm install -g typescript
```

## Getting Started

### What is TypeScript?

TypeScript is a superset of JavaScript, which means all valid JavaScript code is also valid TypeScript code.

### Compiling TypeScript

To compile TypeScript code into JavaScript, you can use the `tsc` (TypeScript Compiler) command followed by the filename:

```bash
tsc filename.ts
```

### Watching for Changes

To continuously watch and compile TypeScript files as you make changes, use the `-w` flag:

```bash
tsc filename.ts -w
```

However, this solution is suitable for compiling a single file. For multiple files, let's set up a `tsconfig.json` file.

## Setting up tsconfig.json

1. Initialize a `tsconfig.json` file in your project directory:

```bash
tsc --init
```

2. Specify the `rootDir` to point to your TypeScript files and `outDir` for the compiled JavaScript files. For example:

```json
{
  "compilerOptions": {
    "rootDir": "./src",
    "outDir": "./build/js",
    ...
  },
  ...
}
```

3. Compile all TypeScript files with the watch mode:

```bash
tsc -w
```

Now, TypeScript will continuously compile all files in the specified `rootDir`.

### Managing Deleted Files

Note that if you delete a TypeScript file, its compiled JavaScript file won't be deleted automatically. You'll need to remove it manually.

### Ignoring Files Outside src

If you want to ignore TypeScript files outside the `src` directory, modify the `tsconfig.json` file:

```json
{
  ...
  "include": ["src"],
  ...
}
```

Now, TypeScript will only compile files within the `src` directory.

### Preventing Compilation on Error

If you want to prevent TypeScript from compiling files with errors, set `noEmitOnError` to `true` in your `tsconfig.json`:

```json
{
  ...
  "compilerOptions": {
    ...
    "noEmitOnError": true,
    ...
  },
  ...
}
```

This ensures that TypeScript only compiles files without errors.

## Conclusion

You've now set up TypeScript in your project, configured `tsconfig.json`, and learned how to compile TypeScript files into JavaScript. Happy coding! 🚀