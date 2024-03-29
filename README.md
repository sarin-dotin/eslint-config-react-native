# Eslint and Prettier config for React Native

## Installing

```bash
# npm
npx install-peerdeps --dev @dotin-tech/eslint-config-react-native
# yarn
npx install-peerdeps --dev @dotin-tech/eslint-config-react-native -Y
```

`.eslintrc`:

```json
{
  "extends": ["@dotin-tech/react-native"],
  "settings": {
    "import/resolver": {
      "babel-module": {}
    }
  }
}
```

`.prettierrc`:

```json
{
  "singleQuote": true,
  "printWidth": 80
}
```

`babel.config.js`:

```js
module.exports = {
  plugins: [
    [
      'module-resolver',
      {
        root: ['./'],
        alias: {
          '^#/(.+)': './src/\\1',
        },
        extensions: ['.js', '.jsx', '.json'],
      },
    ],
  ],
};
```

`jsconfig.json`:

```json
{
  "compilerOptions": {
    "baseUrl": ".",
    "paths": {
      "#/*": ["src/*"]
    }
  },
  "exclude": ["node_modules"]
}
```

`package.json`:

```json
"scripts": {
  "lint": "eslint .",
  "lint:fix": "eslint . --fix"
},
```

## Settings

`.eslintrc`:

```js
{
  "extends": [
    "@dotin-tech/react-native"
  ],
  "rules": {
    "no-console": 2,
    "prettier/prettier": [
      "error",
      {
        "singleQuote": true,
        "printWidth": 100,
      }
    ]
  }
}
```
