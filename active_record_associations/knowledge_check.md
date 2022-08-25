# Learning Outcomes
  - How does Rails normally know which table and foreign key to use when you have an association (e.g. `User.first.posts`)?

  - When would you need to specify the `:class_name` option in an association?

  - What about the `:foreign_key`?

  - What about the `:source`?

  - What is a polymorphic association and when would you use one?

  - What are two ways to use the association to create a new object instead of just calling `YourObject.new`? Why is this useful? Which method is preferred?

  - How do you automatically destroy all a User's Post objects if that user is deleted?

  - How do you set up a self-association, like with Users following Users?