- How does "asset concatenation" optimize loading of your app?
  - it provides a framework to concatenate and compress javascript and css assets
  - it reduces the number of requests a browser makes to render a web page

- How do you include an asset in your views or layout?
  - use javascript_include_tag and stylesheet_link_tag mentioned in 2.3 of Rails asset pipeline doc: https://guides.rubyonrails.org/asset_pipeline.html#coding-links-to-assets

- What does the require_tree method do in a manifest-file?
  - grabs everything in the current directory--tells Sprockets to recursively include all JS files in specified directory into the output

- Why would you namespace your stylesheets?
  - to make a portion of the stylesheet or JS code available to a specific set of views such as having a .container class do something different for a login page versus a checkout page

- How do you display <p>hello world!</p> in your app?
  - use `raw` method in view template or use CGI::escapeHTML method