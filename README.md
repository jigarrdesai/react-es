# react-es

<b> Step -0 : Create packagae.json </b>

npm init -y

<b> Step -1 : Install dependencies </b>

npm install webpack --save-dev
npm install webpack-dev-server --save-dev
npm install babel-core babel-loader babel-polyfill babel-preset-es2015 babel-preset-es2016 babel-preset-es2017 --save-dev

npm install babel-preset-react react react-dom react-bootstrap --save-dev

<b> Step -2 : Create webpack.config.js </b>

module.exports = {
  entry : ['babel-polyfill','./app/index.js'],
  output : {
    path: __dirname + './build',
    filename:'bundle.js'
  },
  module:{
    loaders:[
      {
        loader:'babel-loader',
        test:/\.js$/,
        exclude:/node_modules/
      }
    ]
  },
  devServer:{
    port:3000,
    contentBase:'./build',
    inline: true
  }
}


<b>Step -3 : Add babel preset for es6,es7,es8 in package.json</b>

,
"babel": {
  "presets": [
    "es2015",
    "es2016",
    "es2017",
    "react"
  ]
},

<b> Step -4 : Add react </b>

import React from 'react';</br>
import ReactDOM from 'react-dom'</br>

ReactDOM.render( </br>
  <div> React Application! </div>,document.getElementById('root') </br>
  ); </br>
