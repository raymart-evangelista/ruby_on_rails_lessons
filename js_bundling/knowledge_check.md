# Knowledge Check
- What are the three different options that jsbundling-rails provides?
  - Esbuild, Rollup, and Webpack

- What are the steps to including a bundler for an import map based project?
  - `rails new myapp -j esbuild`
  - if the app is already created..
    - add `gem 'jsbundling-rails'`
    - run `./bin/bundle install`
    - run `./bin/rails javascript:install:esbuild`
    - run `yarn add @hotwired/turbo-rails`
    - run `yarn run build`
    - run `yarn add stimulus`
    - go into `app/javascript/application.js` and change `import "./controllers"` to `import "./controllers/hello_controller.js"`
    - run `yarn run build`

- What is one downside to using JS bundling?
  - any changes to the module will expire the entire bundle, forcing browser to redownload and parse everything all over again--compared to import maps where each module is kept separate meaning you don't have to redownload every single module again

- Why was Webpacker introduced for Rails 6?
  - a Ruby gem created to work with webpack itself which it allowed Rails to use ES6
  - It builds a map of your JS code to build a dependency graph allowing it to generate bundles of code

- Why is the `./bin/dev` command useful in development mode?
  - allows `yarn build --watch` and `rails server` to run at the same time so there's no need to switch between terminal windows for development