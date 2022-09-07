# Knowledge Check
- How does Rails know which type of file you are expecting back when you make an HTTP request?
  - based on the extension of the file ask for

- What is the purpose of the `#respond_to` method?
  - to respond to a request for JSON or XML instead of HTML

- How do you return a User object but specify that you don't want to include certain attributes (i.e. you can't just return `User.first`)?
  - overwrite the `#as_json` method in the User model

- What are the two steps performed behind the scenes by the `#to_json` method?
  - it runs `#as_json` and gets back a hash of attributes which will need to be rendered as JSON
  - then it performs the rendering int JSON using `ActiveSupport::json.encode`--so by modifying `#as_json`, you're specifically targeting the part of the `#to_json` method you want to change

- How do you tell a controller action to render nothing but an error message?
  - `head :some_error_message`

- How do you build your own custom error message?
  - create an ErrorsController, add new methods for errors that render a status, configure the routing for those methods in the routes file. and turn off the default Rails error handling
  - using Heroku may require [extra steps](https://devcenter.heroku.com/articles/error-pages)

- Why can't you use session-based controller authentication methods if you want people to access your API programmatically?
  - You can't rely on browser cookies for authentication

- What is "Service Oriented Architecture"?
  - The app you build will probably have different services within it so instead of building them all under the same master application, they can be broken down into fully independent pieces and have them talk to each other using internally facing APIs