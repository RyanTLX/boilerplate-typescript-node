# TypeScript Node Boilerplate

## Git

Initialise Git Repository

```
mkdir <project name> && cd "$_"
```

```
git init
```

Add .gitignore file

https://www.toptal.com/developers/gitignore?templates=windows,macos,visualstudiocode,node or

```
curl https://www.toptal.com/developers/gitignore/api/node,macos,windows,visualstudiocode > .gitignore
```

## NPM

```
npm init
```

## TypeScript

Install dependencies

```
npm install -D typescript @types/node ts-node
```

Generate tsconfig file

```
npx tsc --init
```

or

```
touch tsconfig.json
```

and paste:

``` json
{
  "compilerOptions": {
    "target": "ES2015",
    "module": "commonjs",
    "strict": true,
    "esModuleInterop": true,
    "skipLibCheck": true,
    "forceConsistentCasingInFileNames": true,
    "resolveJsonModule": true,
    "outDir": "dist",
    "rootDir": "src",
  },
  "include": ["src"],
  "exclude": ["node_modules", "dist"]
}
```

> Above config is based on https://github.com/tsconfig/bases#recommended-tsconfigjson and added in `compilerOptions`:
> ``` json
> "resolveJsonModule": true,
> "outDir": "dist",
> "rootDir": "src"
> ```

Add to package.json scripts

``` json
"build": "rm -rf dist && tsc",
"dev": "ts-node src"
```

Create `src/index.ts` and print Hello World!
```
mkdir src && echo "console.log(\"Hello World\!\");" > src/index.ts
```

## Jest

Install dependency

```
npm install -D jest @types/jest ts-jest
```

Configure TypeScript transpiler for Jest

```
npx ts-jest config:init
```

Create dummy test file

```
touch src/index.test.ts
```

``` TypeScript
describe("Main", () => {
    it("should return true", () => {
        expect(1+1).toBe(2);
    });
})
```

Add to package.json scripts

``` json
"test": "jest --silent"
```

## ESLint

Install dependency

```
npm init @eslint/config
```

Add to package.json scripts

``` json
"lint": "eslint src",
"lint:fix": "eslint src --fix"
```

## Prettier

Install dependencies

```
npm install -D prettier eslint-config-prettier
```

Add extension to eslintrc

``` json
"prettier",
```

Add prettier config and ignore

https://prettier.io/docs/en/options

```
touch .prettierrc.json
```

``` json
{
    "tabWidth": 4,
    "printWidth": 120
}
```

```
touch .prettierignore
```

```
node_modules
dist
coverage
```
