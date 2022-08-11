- How do you make sure a preprocessor runs on your view file?
  - use Embedded Ruby (ERB) which use <%= %> tags

- What is the difference between <%, <%=. and <%#?
  - <%= displays whatever is returned inside the ERB tags (will be used the most)
  - <% will execute the code but what is returned by that line won't actually display anything in the HTML template (purely code-related stuff like if statements and each loops where you don't actually want anything displayed)
  - <%# is used to comment and won't execute

- What does including <%= yield %> in a layout do?
  - identifies a section where content from the view should be inserted

- Why do we use partials?
  - allows code to be more concise and easier to read
  - lets you reuse certain common patterns

- What is the shortcut for rendering a collection as a series of partials?
  - you can write it in the index.html.erb file

- How do you dynamically link to another page of your Rails app?
  - use asset tag helpers