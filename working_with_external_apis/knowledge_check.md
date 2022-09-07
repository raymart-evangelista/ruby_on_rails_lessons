# Learning Outcomes
- How do you set up your app to use an API?
  - register yourself and your app with the provider

- How is API use typically controlled?
  - free tiers of usage, costs for oging over limits

- What is a RESTful API, and how can it make your life easier?
  - APIs that use the HTTP methods like GET/POST/PUT/PATCH/DELETE requests

- What is OAuth?
  - Logging in with a third-party service such that the user doesn't have to give the application their password but instead to the third-party

- What is OmniAuth?
  - a powerful, flexible, and "do as little as possible" library that standardizes multi-provider authentication for web applications

- What is an SDK?
  - Software development kits--usually JS libraries that contain all the code necessary to access their API

# Knowledge Check
- What's the best way to locate an API's docs?
  - Google "company_name API docs"

- What is an API key?
  - A unique identifier for your app to the API provider that is sent along with every request made to that provider

- How do you avoid including an API's secret token in your GitHub repo (e.g. hard coding it)?
  - Use `figaro` gem or environment variables to put the key on the server instead of hard coding it

- Why is it important to know which API version you're using?
  - they can break your app or not work properly if you are using a different version than the doc you are referencing

- Why would a user prefer to sign into your site using Facebook instead of giving you a new password?
  - They only have to remember their Facebook password to log into your site and don't have to trust your site with their password (as long as they trust Facebook)

- What are the different types of "security clearance" for the different types of API requests you can make?
  - You can get Tweets with straightforward and unauthenticated GET requests, the next layer is making requests that include your API key, the next layer is making more sensitive requests like submitting/modifying/deleting data, and the next layer would be to make requests on tehe user's behalf by asking for their user's permissions