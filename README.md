#Configurações do Package.json {

    "@babel/cli": "^7.18.6", // ===>   executar no terminal

    "@babel/core": "^7.18.6" // ===>   biblioteca do babel

    "@babel/preset-env": "^7.18.6", //  ===>   identifica em qual ambiente está sendo executada
                                             para converter da melhor forma possível

    "@babel/preset-react": "^7.18.6", // ===> trabalhar com o react

    "babel-loader": "^8.2.5", // ===>

    "cross-env": "^7.0.3", // ===> criar NODE_ENV= em qualquer sistema operacional

    "html-webpack-plugin": "^5.5.0", //  ===> plugin para gere html no bundle.js

    "webpack": "^5.73.0", //  ===> configuração de compilação

    "webpack-cli": "^4.10.0", //  ===> ler no terminal

    "webpack-dev-server": "^4.9.3" // ===> automatizar a reinderização

}

#configurações do webpack {

    mode: "development", // ===>   modo de desenvolvimento

    devtool: "eval-source-map", //  ===>  visualizar o codigo original da aplicaçao (principalmente nos erros)

    entry: path.resolve(__dirname, "src", "index.jsx"), // ===> caminho de entrada

    output: {path: path.resolve(__dirname, "dist"),filename: "bundle.js",}, // ===>  caminho de saída

    resolve: {extensions: [".js", ".jsx"],}, // ===>  extensões para conversão

    devServer: {allowedHosts: path.resolve(__dirname, "public"),}, // ===>  reiderizar automaticamente

    plugins: [new HtmlWebpackPlugin({
      template: path.resolve(__dirname, "public", "index.html"),}),], // ===> criar html no bundle.js

    module: {rules: [{
      test: /\.jsx$/,exclude: /node_modules/,use: "babel-loader",},],},
      // ===> regras para trabalhar com arquivos nas suas formas

}
