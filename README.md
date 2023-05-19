ESLint Setup For TS React & Next.js

- Install `ESLint` and `Prettier` VSCcode extention.

<br/>

- Install The Packages

```sh $ 
yarn add -D @typescript-eslint/eslint-plugin  @typescript-eslint/parser eslint eslint-config-airbnb eslint-config-airbnb-typescript eslint-config-prettier eslint-import-resolver-typescript eslint-plugin-import eslint-plugin-jsx-a11y eslint-plugin-prettier eslint-plugin-react eslint-plugin-react-hooks prettier
```

<br/>

- Create a `.eslintrc` file in the project root and enter the below contents:

```json
{
  "env": {
    "browser": true,
    "es6": true
  },
  "extends": [
    "eslint:recommended",
    "airbnb/hooks",
    "airbnb-typescript",
    "plugin:react/recommended",
    "plugin:react/jsx-runtime",
    "plugin:@typescript-eslint/recommended",
    "plugin:@typescript-eslint/recommended-requiring-type-checking",
    "plugin:prettier/recommended",
    "plugin:import/recommended"
  ],
  // Specifying Parser
  "parser": "@typescript-eslint/parser",
  "parserOptions": {
    "ecmaFeatures": {
      "jsx": true
    },
    "ecmaVersion": "latest",
    "sourceType": "module",
    "project": "./tsconfig.json" // correct tsconfig file path
  },
  // Configuring third-party plugins
  "plugins": [
    "react",
    "@typescript-eslint"
  ],
  // Resolve imports
  "settings": {
    "import/resolver": {
      "typescript": {
        "project": "./tsconfig.json"
      }
    },
    "react": {
      "version": "18.x"
    }
  },
  "rules": {
    "react/react-in-jsx-scope": 0,
    "react-hooks/rules-of-hooks": "error",
    "no-console": 0,
    "react/state-in-constructor": 0,
    "indent": 0,
    "linebreak-style": 0,
    "react/prop-types": 0,
    "jsx-a11y/click-events-have-key-events": 0,
    "no-unused-vars": "off",
    "no-shadow": "off",
    "arrow-body-style": "off",
    "global-require": 0,
    "react/jsx-filename-extension": [
      1,
      {
        "extensions": [
          ".ts",
          ".tsx"
        ]
      }
    ],
    "prettier/prettier": [
      "error",
      {
        "trailingComma": "es5",
        "singleQuote": true,
        "printWidth": 100,
        "tabWidth": 4,
        "semi": true,
        "endOfLine": "auto"
      }
    ],
    "react/function-component-definition": [
      2,
      {
        "namedComponents": [
          "arrow-function",
          "function-declaration"
        ],
        "unnamedComponents": "arrow-function"
      }
    ]
  }
}

```

<br/>

- Create  `.vscode>settings.json` file in project root folder and enter the bellow contents

```json
{
    "editor.defaultFormatter": "esbenp.prettier-vscode",
    "editor.formatOnSave": true,
    "[javascript]": {
        "editor.formatOnSave": false,
        "editor.defaultFormatter": null
    },
    "[javascriptreact]": {
        "editor.formatOnSave": false,
        "editor.defaultFormatter": null
    },
    "[typescriptreact]": {
        "editor.formatOnSave": false,
        "editor.defaultFormatter": null
    },
    "javascript.validate.enable": false,
    "editor.codeActionsOnSave": {
        "source.fixAll.eslint": true,
        "source.fixAll.tslint": true,
        "source.organizeImports": true
    },
}
```
