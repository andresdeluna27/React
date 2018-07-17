comenzar a configurar el ambiente

npm init

npm install -g babel
npm install -g babel-cli
npm install webpack --save
npm install webpack-dev-server --save
npm install react --save
npm install react-dom --save
npm install babel-core
npm install babel-loader
npm install babel-preset-react
npm install babel-preset-es2015
type nul >index.html
type nul >App.jsx
type nul >main.js
type nul >webpack.config.js


webpack.config.js debe ser así:
***************************************************
var config = {
   entry: './main.js',
   output: {
      path:'/',
      filename: 'index.js',
   },
   devServer: {
      inline: false,
      port: 8080
   },
   module: {
      rules: [
         {
            test: /\.jsx?$/,
            exclude: /node_modules/,
            loader: 'babel-loader',
            query: {
               presets: ['es2015', 'react']
            }
         }
      ]
   }
}
module.exports = config;

******************************************************

en package.json se cambia :"test" "echo \"Error: no test specified\" && exit 1"
por: "start": "webpack-dev-server --hot"

******************************************************
npm install webpack-dev-server -g


++++++++++
Para correr siempre el server será: npm start
++++++++++















