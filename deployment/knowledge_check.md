- What's the minimum number of dynos you need to run your app on Heroku?
  - one dyno

- What are the steps required in order to change your application's domain name to https://the-cool-app.com?
  - purchase domain from a registrar, point it to your herokuapp.com subdomain by changing the appropriate entry in your CNAME file, and tell heroku that you want to point your app to a custom domain

- How do you create a new application with heroku?
  - heroku create

- Which of the database gems are supported by heroku?
  - PostgreSQL

- What are some common ways to tackle deployment errors such as those related to asset pipeline?
  - google, stackoverflow, follow a step by step debugging process
  - modify rails configuration files

- How do you check the server output?
  - heroku logs -t