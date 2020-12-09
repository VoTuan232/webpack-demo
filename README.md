Link: https://www.youtube.com/watch?v=8QYt1_17nk8&list=PLblA84xge2_zwxh3XJqy6UVxS60YdusY8&index=3&ab_channel=ColtSteele

1. Can import/export

2. Loader

npm i --save-dev style-loader css-loader

"style-loader", //3. Inject styles into DOM
"css-loader", //2. Turns css into commonjs
"sass-loader" //1. Turns sass into css
"html-loader" // to automatically require the files we reference in img tags

3. Styling scss
   npm install sass-loader sass webpack --save-dev

4. Cache
   filename: "main.[contentHash].js",

Only 1 file bundle for each version code.

5. Html loader, file loader for static file

6. Clean file when has new rebuild: clean-webpack-plugin

7. Vendor

/vendor usually refers to a directory that contains third party plugins. (bootstrap, jquery,...)


Step 3: Init webpack
- npm i --save-dev webpack webpack-cli
- npm rebuild node-sass
- Run: webpack

Step 6: add loader to load css
- npm i css-loader style-loader

Step 7: add load scss
- npm i sass-loader node-sass

Step 8: Cache busting and HtmlWebpackPlugin

- Configured webpack to use contentHash in bundle file name
- This caused a problem with out script tag in index.html
- We installed HtmlWebpackPlugin to help us generate a new index.html
- It automatically includes the correct script tag at the bottom
- We created a template file that we passed in called template.html
- We deleted the original index.html because we don't need it anymore
- Make sure you are opening dist/index.html now to view the app
- npm i html-webpack-plugin

Step 9: Add prod and dev configs, dev-server

- Broke our webpack.config file into 3 files
- webpack.common.js, webpack.dev.js, and webpack.prod.js
- installed webpack-merge to share the common functionality
- updated our package.json to use the new config files
- installed webpack-dev-server and added it to start script in package.json
- npm i webpack-merge webpack-dev-server

Step 10: Add html-loader, file-loader, and clean-webpack-plugin

- Added html-loader to automatically require the files we reference in img tags
- Added file-loader to handle the svg,png,jpg,gif files from our images
- Configured file-loader to add our images to an imgs directory in dist
- Also configured it to add a hash to their filenames
- Lastly, added clean-webpack-plugin to our production config to clean out the dist directory each time we build
npm i file-loader html-loader clean-webpack-plugin

Step 11: Add entrypoint for vendor js file, add bootstrap js

- Now we have 2 entry files and 2 bundles
- The vendor file houses code that is less likely to change, 3rd party libraries
- The main file has all of our app code

Step 12: Minify JS, CSS, and HTML in production

- Extracted CSS into own file in production
- Minified CSS in production
- Added TerserJS back in to minify JS in production
- Minified HTML in production as well
