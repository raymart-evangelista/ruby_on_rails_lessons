# Learning Outcomes
- What are singular resources?
  - when it makes sense for there to be only one such as a User dashboard which displays interesting facts based on whichever user is logged in; where you would normally require an ID to differentiate which resource is being operated on like #show, since there's only one, the `params[:id]` would no longer be needed

- What are nested routes?
  - for one resource to be nested inside another such as wanting lessons to logically fall within a listing of courses such as `/courses/1/lessons3`
  - when you find yourself working in a controller and needing the parent's ID, the routes should be nested; if the parent's ID isn't needed, it probably doesn't have to be nested

- What are member routes and collection routes?
  - member routes are used to add more non-RESTful route to a resource
  - collection routes are for adding non-RESTful routes to the whole collection of the resource such that you don't have to specify an `:id` attribute

- What is nesting layouts?
  - the ability to render multiple layouts for one page--such as the user pages having a different styling than the home page
    - use the `#content_for` method in the layout view you want to change/remove styling for certain parts of the page, then in the `application.html.erb` layout, catch that content and use it with `#yield`

- What is metaprogramming?
  - the idea that your app creates functions or methods or classes on the fly and can dynamically call them as well
  - i found [this](https://rails-bestpractices.com/posts/2010/07/24/dry-metaprogramming/) linked resource from TOP particularly helpful for refactoring methods that do the same thing but are just dependent on the method name (status)

- What are design patterns?
  - "best practices" for how to code past given situations

# Knowledge Check
- What would the routes file line for a singular resource look like?
  - `resource :user` or `resource :dashboard`
  - notice that `resource` is not plural like `resources :flights`

- How do you nest one resource inside another in the routes file?
  - ```
    {
      resources :courses do
        resources :lessons
      end
    }
    ```

- When do you use the `#member` method?
  - when you want to add a non-RESTful route to a resource
  - ```
    {
      resources :courses do
        member do
          get "preview" # maps to courses#preview
        end
      end
    }
    ```
- When do you use a redirect?
  - when you want to send one route to another route

- What are some techniques for rendering multiple layouts for one page?
  - use `#content_for` in the page layout, then catch the content with `#yield` in the `application.html.erb` layout

- What does the `#send` method do?
  - when you have dynamic situations where you don't know ahead of time what method is going to be called--it's to send that object the method and any arguments you specify--just pass in the symbolized name of the method you want to run on that object

- What are the five design principles represented by the SOLID acronym?
  - Single responsibility
    - a module should be responsible to one thing only--a class should focus on a single concern--don't couple two things that change for different reasons at different times
    - the example given from [wikipedia](https://en.wikipedia.org/wiki/Single-responsibility_principle) says for a module that compiles and prints a report, splitting the compile and report aspects should be done because they are two different responsibilities
  - Open/closed
    - entity can allow its behavior to be extended without modifying the source code
  - Liskov substitution
    - an object and a sub-object must be interchangable without breaking the program
    - in programming specifically, ["if S is a subtype of T, then objects of type T in a program may be replaced with objects of type S without altering any of the desirable properties of that program"](https://en.wikipedia.org/wiki/Liskov_substitution_principle)
  - Interface segregation
    - no code should be forced to depend on methods it does not use
    - splits interfaces that are large into smaller specific ones so clients only have to know about methods that are of interest to them
  - Dependency inversion
    - high level modules shouldn't import anything from low-level modules--both depend on abstractions
    - abstractions should not depend on detials, details should depend on abstractions