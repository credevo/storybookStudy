## storybookStudy

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
  addons: [
   {
     name: '@storybook/addon-postcss',
     options: {
       postcssLoaderOptions: {
         implementation: require('postcss'),
       },
     },
   }
  ]
}
```
