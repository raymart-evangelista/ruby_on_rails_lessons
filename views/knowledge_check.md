- How do you make sure a preprocessor runs on your view file?
  - use the extension `.html.erb`

- What is the difference between <%, <%=. and <%#?
  - <%= displays whatever is returned inside the ERB tags (will be used the most)
  - <% will execute the code but what is returned by that line won't actually display anything in the HTML template (purely code-related stuff like if statements and each loops where you don't actually want anything displayed)
  - <%# is used to comment and won't execute

- What does including <%= yield %> in a layout do?
  - identifies a section where content from the view should be inserted

- Why do we use partials?
  - allows code to be more concise and easier to read
  - lets you reuse certain common patterns such as headers/footers code

- What is the shortcut for rendering a collection as a series of partials?
  - use `<%= render @collection_name %>`

- How do you dynamically link to another page of your Rails app?
  - use `<%= link_to "See All Users", users_path %>` instead of `<a href="<%= users_path %>">See All Users</a>`