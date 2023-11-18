## Custom eslint-config
Personal custom eslint rules for both **styling** and **formatting**.

Applies some common punctuation, spacing and line breaking practices and ES6 syntax enforced.

Whoever sick of Prettier blindly breaking lines are welcomed to try.

## How to use

### dependencies
- requires `eslint` >=8
- requires `@typescript-eslint/eslint-plugin` >=6


### install
```
$ npm install --save-dev @ninthsun91/eslint-config
$ pnpm add --save-dev @ninthsun91/eslint-config
$ yarn add --dev @ninthsun91/eslint-config
```

### configuration example

```js
// .eslintrc.json
{
  "root": true,
  "extends": [
    "@ninthsun91/eslint-config"
  ],
  "parser": "@typescript-eslint/parser",
  "parserOptions": {
    "project": "tsconfig.json",
    "tsconfigRootDir": "."
  },
  "env": {
    "node": true
  },
  "ignorePatterns": [
    "src/api/**",
    "**/*.test.ts",
    "**/*.spec.ts"
  ],
  "rules": {
    "@typescript-eslint/no-explicit-any": "off"
  },
  "overrides": [
    {
      "files": [
        "**/*.test.ts",
        "**/*.spec.ts"
      ],
      "env": {
        "jest": true
      },
      "rules": {
        "max-nested-callbacks": "off"
      }
    }
  ]
}
```