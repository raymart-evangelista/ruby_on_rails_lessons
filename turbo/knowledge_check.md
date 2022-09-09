# Learning Outcomes
- What is a SPA?
  - Single page application used to cut down loading times for the user and the amount of data our app has to send out
  - loads only a single web doc rather than constantly replacing the doc with a brand new one on every request--with SPA a page refresh never occurs

- What is Hotwire?
  - Hotwire is a collection of libraries--Turbo, Stimulus, and Strada--that implement SPA functionality

- What is Turbo and the four components of it?
  - Turbo is used to implement SPA behavior in our Rails app--using four different techniques to create the experience of a speedy SPA without writing JS
  - The four components are:
    - Turbo Drive
    - Turbo Frames
    - Turbo Streams
    - Turbo Native

- When might you use a Turbo Frame?
  - Replacing only a portion of a page during a request
  - Adding a message to a message board
  - Editing the name of an Article directly in an index page of Articles

- How do we use Turbo Streams to update our pages?
  - use `<turbo-stream> elements` to wrap HTML 
  - in the controller, tell it to accept Turbo Stream format similar to how we format a JSON using `format.turbo_stream`, then make a `create.turbo_stream.erb` file

- What do we use Turbo Native for?
  - wraps app inside a mobile friendly shell

# Knowledge Check
- What does SPA stand for & what is it?
  - Single Page Application
  - web app that dynamically rewrites the current web page with new data from the web server, instead of the loading entire new pages--allowing it to act more like a desktop app

- What is Turbolinks?
  - predecesoor ot Turbo

- What is Hotwire?
  - Umbrella term for three different frameworks--Turbo, Stimulus, and Strada

- How do we use a Turbo Frame?
  - use the Rails special helper `<%= turbo_frame_tag %>` on pages we want to connect, and if you want to replace its content with a link that requests a new frame, put the link inside the Turbo Frame where the requested view also includes a Turbo frame with the same ID

- How do we set up Turbo Streams?
  - tell the controller to accept and `respond_to` the `format.turbo_stream`; then set up a `<somethign>.turbo_stream.erb` view file with the Rails special helper `<%= turbo_stream.<action> "objects", @object %>`; which will create a Turbo Stream packet with the action. The target of the action is `"objects"` and will do an action on the `@object`.