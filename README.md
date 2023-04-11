# Best React.JS || Next.JS Linter Setup

The instructions presented here are highly recommended as they provide the most effective configuration for using eslint, prettier and editorconfig together in react.js || next.js.

## Please follow the instructions provided:

```bash
npm i -g eslint
eslint --init
```

### Select this options:

`? How would you like to use ESLint?`

<span style='color:#0aead4'>> To check syntax, find problems, and enforce code style</span>

`? How would you like to define a style for your project?`

<span style='color:#0aead4'>> Use a popular style guide</span>

`? Which style guide do you want to follow?`

<span style='color:#0aead4'>Standard: https://github.com/standard/standard</span>

`? What format do you want your config file to be in?`

<span style='color:#0aead4'>> JSON</span>

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
