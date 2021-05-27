# Using Typescript with Express

Create a **new project** with `npm init`

Install regular **dependencies**

`npm i typescript express`

and **dev-dependencies**

`npm i -D nodemon ts-node prettier @types/express`

**Initialize typescript** with `tsc --init`

Modify `tsconfig.json`

```json
{
  "compilerOptions": {
    "outDir": "./build"
  }
}
```

Add start script to `package.json`

```json
"scripts": {
  "start": "nodemon --watch */* --ext ts,json --exec \"ts-node index.ts\""
}
```
