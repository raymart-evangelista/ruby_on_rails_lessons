- What is a CSRF Token and why is it necessary?
  - cross-site request forgery tokens are used to verify that the form was actually submitted from a page you generated so Rails can match the form with your session and the application

- What is the name attribute of a form input element and what does it do?
  - the name attribute tells Rails what to call the stuff entered in the corresponding input field when it creates the params hash
      - `<input type="text" name="description">` results in the params hash containing a key called description -> params[:description] inside the controller

- How do you nest attributes under a single hash in params?
  - using the name attribute such as with radio buttons using the name attribute to know which radio buttons should be grouped together so that clicking one will unclick another

- How do you pass form_with a model object?
  - specify the model before the do end block--such as `<%= form_with model: @article %>

- How do you access errors for a failed-to-save model object?
  - object_name.errors

- How do Rails forms make PATCH or DELETE requests?
  - Rails sticks a hidden field named "_method" into the form which tells Rails you want to do a PATCH or DELETE request; add this to the form by passing the option `method: ` to form_with

- What is one case where you may need an array of hashes within the params hash?
  - having users be able to input multiple phone numbers
      - `<input name="person[phone_number][]" type="text"/>
          <input name="person[phone_number][]" type="text"/>
          <input name="person[phone_number][]" type="text"/>`
