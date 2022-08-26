# Learning Outcomes
- How does Rails normally know which table and foreign key to use when you have an association (e.g. `User.first.posts`)?
  - Rails knows how to look for the foreign key `post_id`

- When would you need to specify the `:class_name` option in an association?
  - when the foreign key is something else than the default naming so Rails knows where to find the table and foreign key

- What about the `:foreign_key`?
  - when you have two or more types of the model such as two User types, author and editor

- What about the `:source`?
  - when you are making associations in the through table

- What is a polymorphic association and when would you use one?
  - when a single model can belong to many different types of models
  - a user can comment on many types of things posted by other users like text, pictures, images 

- What are two ways to use the association to create a new object instead of just calling `YourObject.new`? Why is this useful? Which method is preferred?
  - you can automatically populate the foreign key `YourObject.AssociatedObject.new` or `YourObject.AssociatedObject.create`
  - you can use the shovel operator to add a new object to the association `Object.AssociatedObjects << AssociatedObject` or `user.posts << post`

- How do you automatically destroy all a User's Post objects if that user is deleted?
  - make the post objects `dependent` in the User model

- How do you set up a self-association, like with Users following Users?
  - do self joins by specifying both associations in the User model with different names
  - `has_many :followers, class_name: "User", foreign_key: "follower_id"`

# Knowledge Check
- What two pieces of information will Rails assume by default for associations?
  - class of the model an association points to is based directly off the name of the association
  - foreign key in any `belongs_to` relationship is called `yourassociationname_id`

- Which type of association may require the `:source` option to be specified?
  - `has-many-through` or `has-one-through` associations

- What is populated automatically when an object is created by an association?
  - the foreign key

- Can a polymorphic association use a single column foreign key?
  - it uses a foreign key id and also a reference to which type of model it corresponds to

- Can a model have associations with instances of the same model?
  - yes through self joins