# Learning Outcomes

- What is an Active Record relation?
  - An active record query that only get executed when it becomes absolutely necessary to know what's inside them

- What is lazy evaluation?
  - Since there's no reason to tell the database to execute a query until the last possible second, nothing will get evaluated until the method on the object gets called
    - if a controller grabs 5 blog posts using @posts = Post.limit(5), a relation is being passed and that query will run and be stored as a real Ruby object in memory when called on

- What are some commonly used Rails query methods?
  - #find, #first, #last, #find_by, #order, #limit
  - https://guides.rubyonrails.org/active_record_querying.html#retrieving-objects-from-the-database

- What are N+1 queries and why are they a concern?
  - grabbing all the records for all your objects such as `User.all` then loop through each user and call an association it has such as `user.city`
  - it's a concern because it results in one query to get all users, then another query for each user to find its city through the association--this can reduce efficiency 

- What are scopes?
  - a custom chain of Active Record methods that can be referenced as method calls on the association objects or models

# Knowledge Check

- How does lazy evaluation help make Active Record more efficient?
  - queries don't have to run until they are called upon, so these queries won't be stored as Ruby objects in memory until they are called on

- How do you check whether a database already contains a record?
  - use the method #class

- What is the difference between a #where query and a #find query?
  - #find returns the actual record while #where returns a relation which acts like an array
  - #where corresponds to the WHERE sql statement--allowing specific conditions to limit records returned
  - #find will retrieve object corresponding to specific primary key that matches any supplied options

- How do you join tables together in Rails?
  - #joins
  - #left_outer_joins

- What is an example of an N+1 query?
  - grabbing all the records for all your objects such as `User.all` then loop through each user and call an association it has such as `user.city`

- What method is used to deal with an N+1 query?
  - #includes which will take the name of one or more associations you want to load at the same time as the original object, and brings them to memory
  - #pluck also allows you to skip several steps in the process of pulling up records, storing them in memory, grabbing a specific column, and placing it into an array--#pluck gives you the resulting array right away

- When would you use a class method in place of a scope?
  - usually when your login chains are more complicated

