# Como usar o Redux Toolkit no React + TS com Vite
Passo a passo do tutorial Quick Start do RTK aplicado no Vite

## 1. Crie um projeto com Vite
Acesse o site [Getting Started | Vite](https://vite.dev/guide/)

## 2. Instale o Redux Toolkit para React
```bash
npm install @reduxjs/toolkit react-redux
```

## 3. Veja o tutorial completo sobre como integrar o Redux Toolkit (RTK) no projeto
Acesse o site [Quick Start | Redux Toolkit](https://redux-toolkit.js.org/tutorials/quick-start)

## 4. Crie e configure o store
Criamos o arquivo store.ts e configuramos com configureStore, adicionando as tipagens específicas.

## 5. Integre ao projeto
Importamos o store e o <Provider> no arquivo main.tsx, na raiz do projeto, para que o estado do RTK seja acessível globalmente.

## 6. Criando o Slice
Criamos o arquivo counterSlice.ts, onde trabalhamos com conceitos de estado inicial, reducers, actions, payload e imutabilidade.

## 7. Vincule o slice ao store
Importe o counterReducer ao store.

## 8. Convertendo o counter react (useState) para RTK (useSelector, useDispatch)
Aqui finalizamos o projeto transformando o contador inicial do Vite em um contador do RTK.

---

# React + TypeScript + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/README.md) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## Expanding the ESLint configuration

If you are developing a production application, we recommend updating the configuration to enable type aware lint rules:

- Configure the top-level `parserOptions` property like this:

```js
export default tseslint.config({
  languageOptions: {
    // other options...
    parserOptions: {
      project: ['./tsconfig.node.json', './tsconfig.app.json'],
      tsconfigRootDir: import.meta.dirname,
    },
  },
})
```

- Replace `tseslint.configs.recommended` to `tseslint.configs.recommendedTypeChecked` or `tseslint.configs.strictTypeChecked`
- Optionally add `...tseslint.configs.stylisticTypeChecked`
- Install [eslint-plugin-react](https://github.com/jsx-eslint/eslint-plugin-react) and update the config:

```js
// eslint.config.js
import react from 'eslint-plugin-react'

export default tseslint.config({
  // Set the react version
  settings: { react: { version: '18.3' } },
  plugins: {
    // Add the react plugin
    react,
  },
  rules: {
    // other rules...
    // Enable its recommended rules
    ...react.configs.recommended.rules,
    ...react.configs['jsx-runtime'].rules,
  },
})
```
