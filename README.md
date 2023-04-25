# Best React.JS || Next.JS Linter Setup

<div style="display: flex">
<img src='./assets/ESLint.webp' width='60px' alt='ESLint'>
<img src='./assets/plus.webp' width='60px' alt='Plus'>
<img src='./assets/prettier.webp' width='60px' alt='prettier'>
<img src='./assets/plus.webp' width='60px' alt='eslint'>
<img src='./assets/editorconfig.webp' width='60px' alt='editorconfig'>
<img src='./assets/equal.webp' width='60px' alt='editorconfig'>
<img src='./assets/Next.js.webp' width='60px' alt='Next.js'>
<img src='./assets/slash.webp' width='27px' alt='next js'>
<img src='./assets/React.webp' width='60px' alt='React'>
</div>

The instructions presented here are highly recommended as they provide the most effective configuration for using eslint, prettier and editorconfig together in react.js || next.js.

## Please follow the instructions provided:

```bash
npm i -g eslint
eslint --init
```

### Select this options:

`? How would you like to use ESLint?`

<ins><span style='color:#0aead4'>> To check syntax, find problems, and enforce code style</span></ins>

`? How would you like to define a style for your project?`

<ins><span style='color:#0aead4'>> Use a popular style guide</span></ins>

`? Which style guide do you want to follow?`

<ins><span style='color:#0aead4'>> Standard: https://github.com/standard/standard</span></ins>

`? What format do you want your config file to be in?`

<ins><span style='color:#0aead4'>> JSON</span></ins>

### Select your package management to proceed with the installation of the required packages.

```bash
mkdir .vscode
cd .vscode
echo {}> settings.json
```

### In the settings.json file :

```jsx
{
  "editor.codeActionsOnSave": {
    "source.fixAll": true,
    "source.fixAll.eslint": true,
  },
  "editor.formatOnSave": true
}
```

```
cd..
echo {}> .editorconfig
```

### Inside .editorconfig file :

```js
root = true

[*]
indent_style = space
indent_size = 2
end_of_line = lf
charset = utf-8
trim_trailing_whitespace = false
insert_final_newline = false
```

```bash
npm i -D prettier eslint-plugin-prettier eslint-config-prettier
```

```bash
echo {}> .prettierrc.yml
```

### Inside .prettierrc.yml file :

```yml
trailingComma: 'es5'
tabWidth: 2
semi: false
singleQuote: true
```

### Add the following to the .eslintrc.json :

```json
{
  "env": {
    "browser": true,
    "es2021": true
  },
  "extends": [
    "plugin:react/recommended",
    "standard",
    "plugin:prettier/recommended"
  ],
  "parserOptions": {
    "ecmaFeatures": {
      "jsx": true
    },
    "ecmaVersion": "latest",
    "sourceType": "module"
  },
  "plugins": ["react"],
  "rules": {
    "react/no-unknown-property": 0,
    "no-unused-vars": "off",
    "prettier/prettier": [
      "error",
      {
        "singleQuote": true,
        "semi": false
      }
    ],
    "react/prop-types": 0
  }
}
```
