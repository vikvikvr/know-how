## Start new project

`npx create-react-app my-app --template typescript`

## Add to existing project

`npm install --save-dev typescript`

```json
"scripts": {
  "build": "tsc"
},
```

`npx tsc --init`

> tsconfig.json

```json
{
  "compilerOptions": {
    "rootDir": "src",
    "outDir": "build"
  }
}
```
