# Pseudo IDE

A web editor for a small made up language called Pseudo. You type code, press run, and the output appears below.


## How the language runs

Three stages, each in `src/app/logic`.

**Lexer** reads the raw text one character at a time and turns it into tokens. A position tracker follows line and column, which is how errors can point at the exact spot.

**Parser** takes those tokens and builds a tree. Each node is one action, an assignment, a loop, a piece of maths. This is where bad structure is caught.

**Interpreter** walks the tree and runs it. A symbol table holds the variables, and a context object holds the current scope and points at its parent, so a function can see the names outside it.

## The app

`code-editor` is where you type. `run-button` calls the interpreter service. `output-console` shows the result or the error. `drag-bar` lets you resize the two panels.

## Run it

This project is from 2020 and needs **Node 14**. On Node 16 or newer it fails during install or with an OpenSSL error at startup.

Check what you have:

```
node -v
```

If it is not 14, install nvm and switch:

```
nvm install 14
nvm use 14
```

Then:

```
npm install
npx ng serve
```

Open http://localhost:4200

## If it still fails

Use `npx ng serve`, not `ng serve`. The second one needs the Angular CLI installed globally, and a newer global CLI will refuse to run an Angular 9 project.

If npm install stops on a peer dependency error:

```
npm install --legacy-peer-deps
```

If you must stay on a new Node version, this works but is a patch, not a fix:

```
export NODE_OPTIONS=--openssl-legacy-provider
npx ng serve
```
