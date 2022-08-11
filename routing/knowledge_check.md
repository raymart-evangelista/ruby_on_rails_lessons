- What is the purpose of the Rails router?
  - the purpose is to match what to display such as a new user webpage or an existing user 
  - it looks for the HTTP verb and the URL being requested to match it with the appropriate controller action to run

- How do you assign the root route of your application in the router?
  - root to: "controller-name#action"
  - an example is like `root to: "cars#index"`

- Assuming we have no knowledge of the HTTP-verb, which 3 RESTful controller actions could be triggered by the /photo/:id -route?
  - show, update, destroy (get, patch/put, delete)

- How can you assign all of the RESTful routes for a resource - excluding the destroy-route - in just one line?
  - `resources :posts, except: :destroy`

- How would you create a link in your app (without hardcoding), that directs you to /photos/10/edit?
  - `link_to "Edit this post", edit_post_path(10)`
  - `edit_photo_path(10)`

- Which Chrome extension can you use to simulate HTTP-requests with an API?
  - Postman