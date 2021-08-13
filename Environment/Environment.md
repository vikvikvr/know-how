# Setting up the Environment

## Prettier

Install prettier

```bash
npm i -D prettier
```

Create 2 scripts in package.json

```json
{
  "scripts": {
    "prettier:check": "prettier --check .",
    "prettier:fix": "prettier --write ."
  }
}
```

Ignore unwanted folders in `.prettierignore`

```
node_modules
build
```

Setup custom rules in `.prettierrc`

```json
{
  "singleQuote": true,
  "semi": true
}
```

## ESLint

npx eslint --init

## VSCode

files: auto save -> onFocusChange
Editor: Format On Save
Editor: Default Formatter

## Husky

npm i -D husky
npx husky install
npx husky add .husky/pre-commit "npm run lint"
npx husky add .husky/pre-push "npm run lint && npm run test"
