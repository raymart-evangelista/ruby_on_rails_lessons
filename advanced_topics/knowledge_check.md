# Learning Outcomes
- What are singular resources?
  - when it makes sense for there to be only one such as a User dashboard which displays interesting facts based on whichever user is logged in; where you would normally require an ID to differentiate which resource is being operated on like #show, since there's only one, the `params[:id]` would no longer be needed

- What are nested routes?
  - for one resource to be nested inside another such as wanting lessons to logically fall within a listing of courses such as `/courses/1/lessons3`

- What are member routes and collection routes?

- What is nesting layouts?

- What is metaprogramming?

- What are design patterns?

# Knowledge Check
- What would the routes file line for a singular resource look like?
  - `resource :user` or `resource :dashboard`
  - notice that `resource` is not plural like `resources :flights`

- How do you nest one resource inside another in the routes file?
  ```
  {
    resources :courses do
      resources :lessons
    end
  }
  ```

- When do you use the `#member` method?

- When do you use a redirect?

- What are some techniques for rendering multiple layouts for one page?

- What does the `#send` method do?

- What are the five design principles represented by the SOLID acronym?