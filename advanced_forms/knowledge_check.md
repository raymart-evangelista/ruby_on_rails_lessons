# Knowledge Check
- What does the `#select_tag` helper do?
  - create the surrounding tag

- When using `#options_for_select`, what format does the array need to be in?
  - gives `#select_tag` the array of options it needs; the format needs to be an array of arrays

- When would you use the `#select` helper?
  - when you want to avoid using `#options_for_select` and the form is designed to build a model instance

- How can you prevent users from having to submit multiple forms?
  - use nested forms so users can create many address objects

- What do you add to the model that allows nested forms to create new objects?
  - use `#accepts_nested_attributes_for`

- How do you allow the nested parameters in your controller?
  - declare the permitted parameters in the controller before passing them to the model

- How can you set up a dropdown or checkbox to delete a record that already exists?
  - make a hidden field in your form (or nested form) that has the same name as your checkboxes or dropdown but only contains the value `""` so that the attribute shows up in `params` hash no matter what