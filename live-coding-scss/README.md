요구사항:)

1. 유저리스트 요청 api 는 다음과 같습니다. https://randomuser.me/api/
- 100개의 results를 요청해주세요.
- 초기 gender 선택값으로 “male” 버튼이 선택 되어있습니다. “female”버튼을 클릭시, 여성에 대한 데이터만을 받아올 수 있게 api 요청해주세요. (반대로 “male”버튼 클릭시, 남성에 대한 데이터만 받아옵니다.)

2. 최초 데이터를 받아올때, “로딩중” 텍스트를 화면에 표시해주세요.
3. 만약 데이터가 없다면, “없음” 텍스트를 화면에 표시해주세요.
4. 데이터를 받아오는 중에 에러가 발생한다면 alert를 이용하여 response의 에러메시지를 노출시켜주세요
5. 화면너비가 960px이상의 화면에서는 유저리스트가 row당 5개가 노출되어야 합니다. 960px보다 작은 화면에서는 유저리스트가 row당 2개가 노출되어야 합니다.



# React + TypeScript + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/README.md) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## Expanding the ESLint configuration

If you are developing a production application, we recommend updating the configuration to enable type aware lint rules:

- Configure the top-level `parserOptions` property like this:

```js
export default {
  // other rules...
  parserOptions: {
    ecmaVersion: 'latest',
    sourceType: 'module',
    project: ['./tsconfig.json', './tsconfig.node.json'],
    tsconfigRootDir: __dirname,
  },
}
```

- Replace `plugin:@typescript-eslint/recommended` to `plugin:@typescript-eslint/recommended-type-checked` or `plugin:@typescript-eslint/strict-type-checked`
- Optionally add `plugin:@typescript-eslint/stylistic-type-checked`
- Install [eslint-plugin-react](https://github.com/jsx-eslint/eslint-plugin-react) and add `plugin:react/recommended` & `plugin:react/jsx-runtime` to the `extends` list
