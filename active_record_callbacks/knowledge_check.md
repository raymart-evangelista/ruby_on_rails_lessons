# Learning Outcomes
- What is a callback used for?
  - It is used to hook into an object's life cycle so you can control the application and its data-- it allows you to trigger logic before/after/around an alteration of an object's state

- What are the major lifecycle stages of an Active Record object?
  - initialize, validate, save, create, update, destroy

- How do you build an "around" callback?
  - use `around_<operation>`

- How do you specify a particular action to run a callback for?
  - register the action with the event callback

# Knowledge Check
- How do you register a callback?
  - put it at the top of the Model by using the appropriate method

- What events happen in an Active Record object's lifecycle?
  - initialized, validated, saved, created, updated, found

- How can you make a callback run under specific conditions?
  - use the `:on`, `:if`, `:unless` options

- When are transaction callbacks most useful?
  - When the Rails app needs to interact with an external application as part of the save process.. and when a save fails, in order to roll back--basically wrapping the database save operation in a transaction where all steps owrk or all fail and are rolled back