# Learning Outcomes
- What is a mailer?
  - allows you to send emails from your application

- How are mailers similar to controllers? To models?
  - creating a new mailer is similar to creating a new controller--and it's like a controller and model in one--the mailer also has actions similar to controller methods

- Why do you need both a text and an HTML version of your mailers?
  - for accessibility and when HTML is disabled, the text version is used--two versions also bypass SPAM filters

- What is an email add-on used for?
  - they are used to handle getting mail delivered and opened so the developer can focus on building the application

- What is the `letter_opener` gem used for?
  - this will take emails and display them to the web browser whenever they would otherwise be sent

# Knowledge Check
- How do you create a new mailer from the command line?
  `rails g mailer <Mailer>` so for example `rails g mailer User`

- Where do you store the actual email in your application?
  - in `app/views/`

- How do you send an email directly from the Rails console?
  - call `#deliver_now` or `#deliver_now!` on the mailer action--for example, `UserMailer.welcome_email(@user).deliver_now!`

- How do you use callbacks with mailers?
  - similar to a normal controller, you can use callbacks like `after_action` to run after the email is generated

- How do you write links in mailer views?
  - use `_url` instead of `_path` because users are opening up the email and clicking the link at an external source

- How do you style an HTML email?
  - use inline style or `<style>` tags