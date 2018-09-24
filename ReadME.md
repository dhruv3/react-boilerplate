# React Boilerplate

From the command line, run:

1. git clone https://github.com/dhruv3/react-boilerplate.git {directory_name}
2. cd {directory_name}
3. npm install
4. npm run start

This boilerplate is created by following the [video lecture by Tyler McGinnis](https://www.youtube.com/watch?v=Zb2mQyQRwqc).

## Notes 
A brief description of the steps followed and their explaination is as follows:
```python
mkdir {boilerplate-folder}
cd {boilerplate-folder}
```
```node
npm init -y 
```
This creates a package.json file for us. ‘y’ flag indicates we want to create package file with default config setting.

Next install 2 package from npm:
```node
npm install react react-dom
```
This command will update package.json file and create a node module folder which has all the dependencies required by our newly installed libs.
```python
vim .gitignore
```
Add node_module and DS_Store to it

Next create React folder with js, css and html files.

Next do babel stuff. We need to tell the browser to read JSX. Using Babel we can help browser in dealing with jsx.

Run this:
```bash
npm install --save-dev @babel/core @babel/preset-env @babel/preset-react webpack webpack-cli webpack-dev-server babel-loader css-loader style-loader html-webpack-plugin
```
`--save-dev` we have used this so as to separate normal dependencies from devDependencies(things we need in order build our app).

Create a `webpack.config.js` file which is a module bundler. Webpack takes all of our modules then intelligently combine them into a single module which can be referred inside the index.html file.
 
Webpack creates a single javascript file for us. We can tell webpack what transformation it can make on the file before it creates it.

We want: all ES6 and JSX into something that browser will understand
```bash
module: {
    rules: [
      {test: /\.(js)$/, use: 'babel-loader'},
      {test: /\.css$/, use: ['style-loader', 'css-loader']}
    ]
  }
```
Here we mention two rules. Rule 1 says that on any js file run the babel-loader on it. Rule 2 says on any single css file run the style loader and then the css loader on it.

css-loader converts code like url(../background.png) to require(..something..).

Style-loader brings in the css content into the page and ensures that css is applied to it.
