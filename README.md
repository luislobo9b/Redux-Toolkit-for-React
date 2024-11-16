# Como usar o Redux Toolkit no React + TS com Vite
Passo a passo do tutorial Quick Start do RTK aplicado no Vite

## 1. Crie um projeto com Vite (React + TS)
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

# Links úteis
[Documentação oficial](https://redux-toolkit.js.org/)

[Create A React Redux App](https://redux-toolkit.js.org/introduction/getting-started#create-a-react-redux-app)

## Extensão para navegador (veja o histórico de atualizações no estado)
[Redux DevTools - Chrome](https://chromewebstore.google.com/detail/redux-devtools/lmhkpmbekcpmknklioeibfkpmmfibljd)

[Redux DevTools - Firefox](https://addons.mozilla.org/pt-BR/firefox/addon/reduxdevtools/)

---

# Glossário Redux Toolkit (RTK)
### **Store**
Centraliza o estado e os métodos de gerenciamento no Redux.

- Importa o `configureStore` do RTK.

**Exemplo:**

`import { configureStore } from '@reduxjs/toolkit';`

- Importa os reducers dos slices.

**Exemplo:**

`import counterReducer from './counterSlice'; const store = configureStore({ reducer: { counter: counterReducer } });`

### **Slice**
Parte do estado com reducers e actions específicas.

- Importa o `createSlice` do RTK.

**Exemplo:**

`import { createSlice } from '@reduxjs/toolkit';`

- Contém: **Reducers** (lógica de atualização do estado) e **Actions** (geradores de ações).
- Depende do **Immer** internamente para manipulação imutável.
- Exporta as **actions** para o código e o **reducer** (por padrão) para o store.
**Exemplo:**

`export const { increment, decrement } = counterSlice.actions; export default counterSlice.reducer;`

### **app.js**
- Importa o `store`.

**Exemplo:**

`import store from './store';`

- Importa as **actions** do slice.

**Exemplo:**

`import { increment } from './counterSlice';`

### **Reducers**
Funções que atualizam o estado com base em uma ação.

### **Actions**
Objetos que descrevem eventos para mudar o estado.

### **Select**
Função para acessar valores do estado atual usando a função getState

## **selectCounter (getCounter)**
- Seleciona um valor do estado atual.

**Exemplo:**

`function selectCounter() { return store.getState().counter.value; }`

### **Dispatch**
Envia ações para alterar o estado.

## **setCounter**
- Atualiza o estado usando `dispatch`.

**Exemplo:**

`store.dispatch(setCounter(value));`

### **Subscribe**
Escuta mudanças no estado do store.

- Inscreve-se no `store` para receber atualizações.

**Exemplo:**

`store.subscribe(() => { console.log('State changed:', store.getState()); });`

### **State**
O estado atual armazenado no store.

- O estado atual do `store`.

**Exemplo:**

`const state = store.getState();`

### **Payload**
Dados enviados junto com uma ação

- A informação enviada em uma **action**.

**Exemplo:**

`const action = { type: 'counter/increment', payload: 10 };`

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
