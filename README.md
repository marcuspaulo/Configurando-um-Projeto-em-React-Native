# Criando um projeto em React-native

```sh
$ react-native init Githuber
```

# 1 - Criar/Ajustar o arquivo ESLint

.eslintrc.json

```js
{
  "parser": "babel-eslint",
  "extends": ["airbnb", "plugin:react-native/all"],
  "plugins": ["react-native", "jsx-a11y", "import"],
  "env": {
    "jest": true
  },
  "rules": {
    "react/jsx-filename-extesion": [
      "error",
      {
        "extensions": [".jsx", ".js"]
      }
    ],
    "import/prefer-default-export": "off"
  },
  "globals": {
    "__DEV__": true
  },
  "settings": {
    "import/resolver": {
      "babel-plugin-root-import": {}
    }
  }
}

```

# 2 - Configurar o editorconfig (existe um plugin do VSCode)

```js
root = true

[*]
charset = utf-8
indent_style = space
indent_size = 2
end_of_line = lf
insert_final_newline = true
trim_trailing_whitespace = true
```

# 3 - Configurar o arquivo .babelrc (Root import)

```js
{
  "presets": ["module:metro-react-native-babel-preset"],
  "plugins": [
    [
      "babel-plugin-root-import",
      {
        "rootPathSuffix": "src"
      }
    ]
  ],
  "env": {
    "production": {
      "plugins": [
        "babel-plugin-root-import",
        {
          "rootPathSuffix": "src"
        }
      ]
    }
  }
}

```

# 3 - Configurar o Reactotron

3.1 - Criar o arquivo: ReactotronConfig.js, dentro da pasta /src/config

```js
import Reactotron from "reactotron-react-native";

if (__DEV__) {
  const tron = Reactotron.configure() // controls connection & communication settings
    .useReactNative() // add all built-in react native plugins
    .connect(); // let's connect!

  console.tron = tron;

  tron.clear();
}
```

# Adicional: Settings do Visual code

```js
{
  //Define o tema do VSCode
  "workbench.colorTheme": "Dracula",

  // Configura tamanho e família da fonte
  "editor.fontSize": 14,
  "editor.lineHeight": 20,
  "editor.fontFamily": "Fira Code",
  "editor.fontLigatures": true,

  "workbench.iconTheme": "material-icon-theme",
  "window.zoomLevel": 1,

  "prettier.eslintIntegration": true,
  "editor.formatOnSave": true,

  "emmet.includeLanguages": {
    "nunjucks": "html"
  },
  "git.path": "/usr/bin/git",
  "eslint.autoFixOnSave": true,
  "eslint.alwaysShowStatus": true,
  "javascript.format.enable": false,
  "git.autofetch": true,
  "colorize.ignore_search_variables_info": true
}

```
