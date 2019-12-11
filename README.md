# VSCode - ESLint, Prettier & Airbnb Setup

### 1. Install [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) & [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) extensions for VSCode

### 2. Bootstrap a react app

```
npx create-react-app my-app
cd react-app
```

### 3. Install Packages

```
npm i -D eslint prettier eslint-plugin-prettier eslint-config-prettier  eslint-config-react-app eslint-config-airbnb
```

### 3. Create .eslintrc.json file

```
{
  "name": "my-app",
  "version": "0.1.0",
  "private": true,
  "dependencies": {
    "@testing-library/jest-dom": "^4.2.4",
    "@testing-library/react": "^9.3.2",
    "@testing-library/user-event": "^7.1.2",
    "react": "^16.12.0",
    "react-dom": "^16.12.0",
    "react-scripts": "3.3.0"
  },
  "scripts": {
    "start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test",
    "eject": "react-scripts eject"
  },
  "browserslist": {
    "production": [
      ">0.2%",
      "not dead",
      "not op_mini all"
    ],
    "development": [
      "last 1 chrome version",
      "last 1 firefox version",
      "last 1 safari version"
    ]
  },
  "devDependencies": {
    "eslint": "^6.7.2",
    "eslint-config-airbnb": "^18.0.1",
    "eslint-config-prettier": "^6.7.0",
    "eslint-config-react-app": "^5.1.0",
    "eslint-plugin-node": "^10.0.0",
    "eslint-plugin-prettier": "^3.1.1",
    "prettier": "^1.19.1"
  }
}
```

### 5. Edit VSCode settings.json

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
