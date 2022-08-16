- What is an ORM?
  - Object-Relational-Mapping

- Why is Active Record more useful than just using SQL?
  - You can interact with data as though it was a normal Ruby object instead of having to write SQL statements
  - Active Record allows the developer to focus on writing application code while it does the nitty gritty details of connecting the developer to the database
  - By running `rails db:migrate`, Rails executes the proper SQL code to set up the database table so the developer can work on the website

  - represent models and their data
  - represent associations between these models
  - represent inheritance hierarchies through related models
  - validate models before they get persisted to the database
  - perform database operations in an object-oriented fashion

- What are the two steps required to make a new row in your database table with ActiveRecord?
  - First, create with Object#new and pass it hash attributes such as `u = User.new(name: "Sven", email: "sven@theodinproject.com")`
  - Second, save the model into the database with Object#save call such as `u.save`
  - Note that you can run both steps with Object#create such as `u = User.create(name: "Sven", email: "sven@theodinproject.com")`

- What are "generators" in Rails?
  - create MVCs

- Should Active Record model classes be singular or plural?
  - singular

- Which rails command will undo a database migration?
  - `rails db:rollback` will reverse the last series of migrations made
  - don't rollback migrations unless you've screwed up--in cases for removing a column because you no longer need it, you can create a new migration that removes that column using #remove_column

- What does the validation helper presence: true enforce?
  - checks if the value is either nil or a blank string

- How can you see why an instance of a model class has failed validation?
  - use errors[:attribute] which returns an array of all the errror messages for the :attribute

- If class A has a belongs_to association with class B, which class's database table should contain a foreign key?
  - class B has the foreign key because it's the table for declaring the belongs_to association 