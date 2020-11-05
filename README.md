Link: https://www.youtube.com/watch?v=8QYt1_17nk8&list=PLblA84xge2_zwxh3XJqy6UVxS60YdusY8&index=3&ab_channel=ColtSteele

1. Can import/export

2. Loader

npm i --save-dev style-loader css-loader

"style-loader", //3. Inject styles into DOM
"css-loader", //2. Turns css into commonjs
"sass-loader" //1. Turns sass into css

3. Styling scss
   npm install sass-loader sass webpack --save-dev

4. Cache
   filename: "main.[contentHash].js",

Only 1 file bundle for each version code.

5. Html loader, file loader for static file

6. Clean file when has new rebuild: clean-webpack-plugin

7. Vendor

/vendor usually refers to a directory that contains third party plugins. (bootstrap, jquery,...)
