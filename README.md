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
//create folder:  src, src/SCSS, src/index.ts, src/components 
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
