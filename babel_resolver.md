# Babel Resolver
#### Definir a pasta src como padrao do projeto, caminho relativo, remover o './'

`yarn add babel-plugin-module-resolver eslint-import-resolver-babel-module --dev`

* Dentro do arquivo .babelrc colocar as seguintes configs

```json
{
  "presets": ["react-native"],
  "plugins": [
    [
      "module-resolver",
      {
        "cwd": "babelrc",
        "root": ["./src"],
        "extensions":[".js", "ios.js", "android.js"]
      }
    ]
  ]
}
```

* Logo apos salvar e fechar o *.babelrc*, abra o arquivo *.eslintrc* e logo acima da opção "dev", inserir o seguinte codigo, ou acima do globals

```json
"settings": {
  "import/resolver": {
    "babel-module": {}
  }
},
```
