- What does a controller do?
  - The controller acts as the middleman which knows what to ask the Model
  - The controller also knows which view it wants to render and send back to the browser
  - it is responsible for making sense of the request and producing appropriate output
  - it makes the model data available to the view, so it can display that data to the user, and it saves or updates user data to the model

- Why is it important to adhere to the Rails naming convention for your controllers and all of its methods?
  - It allows the developer to find files easier
  - allows you to use the default route generators without needing to qualify each :path tp :controller

- What is the difference between render and redirect_to?
  - rendering is the result of the controller action
  - redirect_to is the result of showing a user a new page instead of the result of a controller action
  - redirect is treated as a new HTTP request

- Which variable in your controller contains all the data sent in by the user?
  - params

- Data from a client can never be trusted. Which helper method should you incorporate in your controller to prevent malicious data injections?
  - allowed_post_params

- When is a flash message shown?
  - it's shown when you get redirected to the next page
  - special part of the session which is cleared with each request

- How do we change when a flash is shown?
  - flash.now