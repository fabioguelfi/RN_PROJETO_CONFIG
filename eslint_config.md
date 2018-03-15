## Eslint config - baseado nas config do airbnb

- #### Primeiro instalar o eslint global

`yarn global add eslint`

*(no seu editor de texto instalar o pacote do eslint)*

Vscode
>[marketplace visualstudio](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint "marketplace visualstudio")

Atom
>[marketplace atom](https://atom.io/packages/linter-eslint "marketplace atom")

------------


- #### Verificar a ultima versao do eslint-airbnb

`npm info "eslint-config-airbnb@latest" peerDependencies`
```json
{
	'eslint': '^4.9.0',
	'eslint-plugin-import': '^2.7.0',
	'eslint-plugin-jsx-a11y': '^6.0.2',
	'eslint-plugin-react': '^7.4.0'
}
```
pegar a depedencia de retorno e inserir no package.json,
```json
{
	'eslint': '^4.9.0',
	'eslint-plugin-import': '^2.7.0',
	'eslint-plugin-jsx-a11y': '^6.0.2',
	'eslint-plugin-react': '^7.4.0'
}
```

------------

- ####Rodar comandos para instalar dependencias 

`yarn || npm install`

logo apos instalar as dependencias acima, instalar os seguintes pacotes

`yarn add babel-eslint eslint-config-airbnb eslint-plugin-react-native --dev`

depois de instalar todas as dependencias criar criar o arquivo *.eslintrc*, na pasta raiz com seguinte codigo

> [.eslintrc](https://gist.github.com/diego3g/fdc8dc51fd60b88e2e3611fb1b59d380 ".eslintrc")

ou
```json
{
  "parser": "babel-eslint",
  "env": {
    "browser": true,
    "jest": true
  },
  "plugins": ["react-native", "jsx-a11y", "import"],
  "extends": ["airbnb", "plugin:react-native/all"],
  "rules": {
    "react/jsx-filename-extension": [
      "error",
      {
        "extensions": [".js", ".jsx"]
      }
    ],
    "global-require": "off",
    "no-console": "off",
    "import/prefer-default-export": "off",
    "no-unused-vars": [
      "error",
      {
        "argsIgnorePattern": "^_"
      }
    ],
    "arrow-body-style": 0,
    "no-underscore-dangle": "off",
    "arrow-parens": [2, "as-needed"],
    "semi": "off",
    "function-paren-newline": ["error", "consistent"]
  },
  "settings": {
    "import/resolver": {
      "babel-module": {}
    }
  },
  "globals": {
    "__DEV__": true
  }
}
```