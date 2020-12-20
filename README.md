# Create a react starter app without using the `create-react-app` command

- npm i react react-dom
- npm i -D @babel/core @babel/preset-env @babel/preset-react babel-loader
- npm i -D webpack webpack-dev-server html-webpack-plugin webpack-cli@3.3.8

## Create a `.babelrc` file

Add the line:
`{ "presets": ["@babel/preset-env", "@babel/preset-react"] }`

## Create a `webpack.config.js` file

Add the code

```
const path = require("path");
const htmlWebpack = require("html-webpack-plugin");
const HtmlWebpackPlugin = require("html-webpack-plugin");

module.exports = {
  entry: "./src/index.js",
  output: {
    path: path.join(__dirname, "dist"),
    filename: "index_bundle.js",
  },
  module: {
    rules: [
      {
        test: /\.js$/,
        exclude: /node_modules/,
        use: {
          loader: "babel-loader",
        },
      },
    ],
  },
  plugins: [
    new HtmlWebpackPlugin({
      template: "./src/index.html",
    }),
  ],
};
```

## Create a `src` directory and a `components` sub-directory

### Create `index.html` and `index.js` files in the `src` directory

### Create the App component in the `components` sub-directory
