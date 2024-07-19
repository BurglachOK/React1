# React + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/README.md) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh


npm create vite@latest

Після створення проекту слідуйте інструкціям.

Встановіть залежності проекту командою npm install
Запустіть проект командою npm run dev

npm install eslint

Останнім кроком буде невеличка зміна налаштувань лінтера ESLint. У файлі налаштувань .eslintrc.cjs потрібно відключити одне непотрібне нам правило. Зокрема, додайте до блоку rules властивість react/prop-types із значенням 0.

Ви можете просто взяти наступний код, який містить потрібні налаштування, і замінити ним вміст файлу .eslintrc.cjs.

module.exports = {
  root: true,
  env: { browser: true, es2020: true },
  extends: [
    "eslint:recommended",
    "plugin:react/recommended",
    "plugin:react/jsx-runtime",
    "plugin:react-hooks/recommended",
  ],
  ignorePatterns: ["dist", ".eslintrc.cjs"],
  parserOptions: { ecmaVersion: "latest", sourceType: "module" },
  settings: { react: { version: "18.2" } },
  plugins: ["react-refresh"],
  rules: {
    "react/prop-types": 0,
    "react-refresh/only-export-components": [
      "warn",
      { allowConstantExport: true },
    ],
  },
};


Додаємо опцію генерування Source Maps у файл налаштувань Vite, який розташований у кореневій папці проекту. Відкрий файл vite.config.js та заміни його вміст на наступний код.

import { defineConfig } from "vite";
import react from "@vitejs/plugin-react";

// https://vitejs.dev/config/
export default defineConfig({
  plugins: [react()],
  build: {
    sourcemap: true,
  }
});

Опис типів пропсів не є обов'язковим. Крім того, що типізація пропсів може заощадити час при виявленні помилок, весь процес типізації займає час розробника, так як це додатковий код. Використовуйте цю можливість лише за бажанням.

Пакет prop-types надає низку валідаторів для перевірки коректності отриманих типів даних під час виконання коду, повідомляючи про невідповідності в консолі.

npm install --save-dev prop-types

npm install clsx

npm install modern-normalize

npm install react-icons





LINKS
https://react.dev/learn/react-developer-tools
https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint
https://vitejs.dev/
https://react.dev/
https://vercel.com/
https://react.dev/learn/your-first-component#components-ui-building-blocks
https://react.dev/learn/writing-markup-with-jsx
https://react.dev/learn/passing-props-to-a-component
https://react.dev/learn/conditional-rendering
https://react.dev/learn/rendering-lists
https://react.dev/reference/react/StrictMode
https://github.com/facebook/prop-types?tab=readme-ov-file#prop-types--
https://github.com/postcss/autoprefixer
https://www.npmjs.com/package/clsx
https://www.npmjs.com/package/modern-normalize?activeTab=readme
https://react-icons.github.io/react-icons/

https://fson-105.vercel.app/