# VSCode - ESLint, Prettier & Airbnb Setup

### 1. Install [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) & [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) extensions for VSCode
Fot this example no changes were made to the default global configurations for both extensions

### 2. Bootstrap a react app

```
npx create-react-app my-app
cd react-app
```
### 3. Delete the entry "eslintConfig" from package.json
```
"eslintConfig": {
    "extends": "react-app"
  },
```
### 4. Install Packages

```
npm i -D eslint prettier eslint-plugin-prettier eslint-config-prettier  eslint-config-react-app eslint-config-airbnb
```

### 5. Create .eslintrc.json file

```
{
  "extends": ["airbnb", "prettier/react"],
  "plugins": ["prettier", "react"],
  "rules": {
    "prettier/prettier": [
      "error",
      {
        "singleQuote": true,
        "trailingComma": "es5"
      }
    ],
    "no-unused-vars": "warn",
    "no-console": "off",
    "func-names": "off",
    "no-process-exit": "off",
    "object-shorthand": "off",
    "class-methods-use-this": "off",
    "react/jsx-filename-extension": [
      1,
      {
        "extensions": [".js", ".jsx"]
      }
    ]
  }
}
```

### 6. Edit VSCode settings.json

```js
{
    // VSCode settings
    "editor.formatOnSave": true,
    // turn it off for JS and JSX, we will do this via eslint
    "[javascript]": {
        "editor.formatOnSave": false
    },
    "[javascriptreact]": {
        "editor.formatOnSave": false
    },
    //ESLINT settings
    // ESLINT status
    "eslint.alwaysShowStatus": true,
    // tell the ESLint plugin to run on save
    "eslint.autoFixOnSave": true,
    // Prettier settings
    // Optional BUT IMPORTANT: If you have the prettier extension enabled for other languages like CSS and HTML, turn it off for JS since we are doing it through Eslint already
    "prettier.disableLanguages": [
        "javascript",
        "javascriptreact"
    ],
    "prettier.trailingComma": "es5",
    "emmet.includeLanguages": {
        "javascript": "javascriptreact"
    }
}
```

### Reference

- ESLint Rules - https://eslint.org/docs/rules/
- Prettier Options - https://prettier.io/docs/en/options.html
- Airbnb Style Guide - https://github.com/airbnb/javascript
