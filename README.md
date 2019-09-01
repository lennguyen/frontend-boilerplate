Webpack project starter with Pug, Sass/Stylus, jQuery, Babel and Yarn
===================

The purpose if this webpack starter is to allow people to create websites without frameworks/libraries like React, Angular, Vue and only using simple but powerful technologies to build quality websites.

## Technologies used

- Templating: `Pug` (This is a template engine and is a fastest way to write HTML)
- Styling: `Sass` (This is a CSS preprocessor which is used to write styles)
- Scripting: `jQuery or plain Javascript`
- JS Compiler: `Babel ES6`
- CSS framework: `Bootstrap`
- Bundler: Webpack (A module bundler to manager all the dependencies of your website)

## Features

- Well organized folder structure for view, styles and assets.
- Webpack notifier on every compilation.
- Compatibility with `manifest`, `browserconfig` and other external files you wish to include.
- `Babel module resolver` configured to use alias and simplify the paths you need to import.
- `Editorconfig`
- Yarn instead NPM
- PostCSS


This guide is a template that contains steps to install the project, technologies used, folder structure, etc.

#

#### <a id="routes">Routes/pages of the website</a>

* `/`: Page to show the home or main page
* `/blog`: Page for blog
* `/contact`: Page for contact

#### Dependencies

* Git https://git-scm.com/downloads
* NodeJS >= 6 https://nodejs.org
* Yarn: `brew install yarn` or follow the specific guide for your OS https://yarnpkg.com/lang/en/docs/install/

#
# 
# Guide to continue developing

#### Dependencies

* Webpack and webpack dev server: Install them with `yarn global add webpack webpack-dev-server`

#### Branches
* `master` main branch, used for production.

#### Process of development

###### Omit the Cloning step if you already have the code in your computer
##### Cloning  (new folder/computer)

1. Clone the `master` branch of the repository first `git clone git@github.com:my-user/my-repo.git`

##### Developing
2. Open the folder `my-repo` in your code editor because that one contains the source code.
3. Start the `development server` of the project with `yarn run dev` (if you want to test the development server in your local network, you should run `yarn run dev-network` instead and with the IP of your host computer, you can access to the website in your other devices)
5. Check the available [routes](#routes) of your website.
6. Perform all the modifications you need


##### Compiling to production
5. In order to generate the production package, press `CTRL + C` to stop the development server and run the command `yarn run prod` and the production build is going to be generated in the `dist` folder.

#### Testing
6. You should always test the production package in your local before push to the repository, open the `dist` folder in your explorer/finder and open the `index.html` with your browser or
7. use the recommended way installing `http-server` with `yarn global add http-server` and inside the `dist` folder run the command `http-server -p 9090` to finally open the url `http://localhost:9090` to see the production package in action.


#
#
# Project structure

* `node_modules`: Contains all the javascript dependencies, you don't need to worry about this and also you should't modify any file there.
* `dist`: Your production code will be placed here, the final package ready to install in your server. No changes are necessary here as this is automatically generated from your source files.
* `src`: All of the source code is contained here... assets, js, scss, jade files, etc. **Any changes you want to make to the website must be done here.**
  * `assets`: All the images, icons, static js files and the fonts needed to run the site. Any new assets must be placed here.
  * `files`: Contain the PDFs of the guides.
  * `styles`: All the CSS(SASS) styles separated into folders to have a modular structure.
  * `views`: You can create more pages in this folder using JADE (.jade) instead of writing pure HTML.
    * `guides`: The JADE file for each guide page, you can add more guides in this place or edit their content of the current ones.
    * `layouts`: The main template files which contain your header and your footer used for all the guides. This is very useful to avoid putting the same header and footer in each guide, or webpage.
    * `mixins`: Pieces of JADE files that are used for the same purpose of the layouts, which is to avoid repeat code in each guide template and instead use a mixing to place the same menu, share bar, page title, etc. just passing an attribute for each one.
* `.editorconfig`: Used to set a configuration for your editor code, like use spaces instead tabs, the charset, of the files, etc.
* `.gitignore`: Here is where you can set which files/folders shouldn't be tracked by `git`, that means, the file/folder written in this file will not be pushed to the repository such as `node_modules` and `dist` folder.
* `browserslistrc`: Share target browsers between different front-end tools, like Autoprefixer, Stylelint and babel-preset-env
* `package.json`: When you run the command `yarn install`, the packages installed are the ones listed in this file with the version that were installed, if you need to add more packages you can do it runing the command `yarn add package_name --save ` then a new package will be installed in the `node_modules` folder and the `package.json` will be updated with a new line of the package added.
* `webpack.config.js`: This is one of the most important files because it's the one that builds the production package and also the development environment, compiling the SASS and Jade files into HTML and CSS code. It also minifies all the files.


### Check Updates: package.json
* `https://www.npmjs.com/package/npm-check-updates`: npm-check-updates upgrades your package.json dependencies to the latest versions, ignoring specified versions. 