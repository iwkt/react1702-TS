# React TypeScript eslint prettier 環境構築

## アプリの作成

今回は react-typescript というアプリ名で作成した

`npx create-react-app react-typescript --template typescript`

## React version down 18 => 17

`npm uninstall react react-dom`

`npm install(yarn add) react@17.0.2 react-dom@17.0.2`

17.0.2 のインストールが終了したら index.tsx を下記へ書き換える

```
import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';
import App from './App';
import reportWebVitals from './reportWebVitals';

ReactDOM.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>,
  document.getElementById('root')
);
// If you want to start measuring performance in your app, pass a funcLon
// to log results (for example: reportWebVitals(console.log))
// or send to an analyLcs endpoint. Learn more: hPps://bit.ly/CRA-vitalsreportWebVitals();

```

## ESLint 導入

### ライブラリをインストール

`yarn add -D eslint @typescript-eslint/eslint-plugin @typescript-eslint/parser`

### .eslintrc.js を作成

```
{
  "env": {
    "browser": true,
    "node": true,
    "es2021": true
  },
  "extends": [
    "eslint:recommended",
    "plugin:react/recommended",
    "prettier"
  ],
  "parserOptions": {
    "ecmaFeatures": {
      "jsx": true
    },
    "ecmaVersion": "latest",
    "sourceType": "module"
  },
  "plugins": ["react","prettier"],
  "rules": {
    "react/react-in-jsx-scope": "off"
  }
}

```

## Prettier 導入

### ライブラリをインストール

`yarn add -D prettier eslint-config-prettier eslint-plugin-prettier`

## .prettierrc を作成

```

{
  "printWidth": 120,
  "useTabs": false,
  "semi": true,
  "singleQuote": true,
  "trailingComma": "es5",
  "bracketSpacing": true,
  "jsxBracketSameLine": false
}

```

## 実行

`npm start`
