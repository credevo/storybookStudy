### storybookStudy

## scss storybook setting

npm init -y

npm i -D react react-dom

npm i typescript -g

npm i -D typescript @types/react

tsc --init

//tsconfig.js

```js
"compilerOptions" : {
    ...
    "jsx": "react",
    ...
    "module": "es6",
    ...
    "moduleResolution": "node",
    ....
    "outDir": "./dist",
    ....
  }
```

//create folder: src, src/SCSS, src/index.ts, src/components
npx sb init --builder webpack5

//npm i -D @storybook/addon-postcss

npm i -D sass style-loader css-loader sass-loader
//.storybook/main.js

```js
module.exports = {
  ...
  core: {
    builder: "@storybook/builder-webpack5",
  },
  ...
  webpackFinal: async (config, { configType }) => {
    config.module.rules.push({
      test: /\.scss$/,
      use: ["style-loader", "css-loader", "sass-loader"],
      include: path.resolve(__dirname, "../"),
    });
    return config;
  },
}
```

####reference url

markdown cheet : https://gist.github.com/stevenyap/7038119
https://dev.to/iamrishupatel/how-to-create-a-react-component-library-using-storybook-typescript-scss-and-rollup-4pin
https://github.com/storybookjs/storybook/issues/17768
https://storybook.js.org/blog/storybook-for-webpack-5/
https://gist.github.com/shilman/8856ea1786dcd247139b47b270912324#upgrade
https://github.com/storybookjs/presets/blob/master/packages/preset-scss/README.md
https://stackoverflow.com/questions/71630324/cannot-import-scss-module-styles-the-same-way-with-storybook-and-gatsby

---
