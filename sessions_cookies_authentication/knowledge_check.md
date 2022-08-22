# Learning Outcomes

- What is a cookie?
  - key/value data pairs stored in a user's browser till specified expiration date
  - used to bookmark user's place in a web page, store shopping cart info, or passwords
  - avoid storing anything in regular browser cookies that need to be secure or persisted across browser sessions

- What is a session?
  - how a website keeps track of how a user is logged in when the page reloads

- How is the session "hash" different from cookies "hash?
  - session hash is an entire hash that gets put in the secure session cookie that expires when the user closes the browser
  - cookies hash gets stored as an individual cookie and are stored in the user's browser till a specified expiration date

- What is the flash "hash" used for?
  - a session hash that self destructs after it's opened, commonly used to send messages from controller to view so user can see success/failure messages after form submissions

- When would you use flash.now instead of flash?
  - in cases where users can't sign up because of failed validations, flash.now can be used to have error messages available immediately

- What are controller filters and why are they useful?
  - controller filters can be used to run code in your controller at very specific times such as before any other code runs
  - useful for filtering out unauthorized requests such as a user requesting to run an action they aren't authorized to make

- How do you run a controller filter for just a specific few actions?
  - use "only" option such as `before_action :require_login, only: [:edit, :update]`
  - can also use "except" option such as `before_action :require_login, except: [:create]`

- What's the difference between authentication and authorization?
  - authentication is to make sure a user is who they say they are
  - authorization is different levels of access for different user classes such as logged in vs not logged in

- Why is #has_secure_password a handy method?
  - it intercepts password values and converts them into password digest for you

- What is the basic overview of how to authenticate a user with that method?
  - create a column in the Users table that contains the user's password_digest, then once a user signs up turn the password into a digest form, then store that in a new database column by adding #has_secure_password to the User model, add corresponding validations for password, add a sessions controller and its routes and use #authenticate to sign in the user when proper credentials are submitted in the signin form, then allow the user to be remembered by creating a remember_token column in the Users table and saving that token as a permanent cookie in the user's browser with a reset on each new signin, then on each page load that requires authentication check the user's remember_token cookie against the database to see if the user is signed in (if not, redirect to signin page; also make helper methods that let you determine if a user is signed in or do things like compare another user to the currently signed in user)

- What additional steps (on a high level) are needed to actually "remember" a user after they've closed the browser?
  - having a remember_token column in the Users table that is a permanent cookie in the user's browser

- What is the Devise gem and why is it useful?
  - a gem built to handle authentication and is useful because it prepackages many signin/signup forms and methods to implement

# Knowledge Check

- How would you set a cookie for hair color on a user's browser?
  - cookies[:hair-color] = { value: "blonde, expires : Time.now + 3600 } or cookies[:hair-color] = "blonde"

- How would you require a user is logged in before running some code?
  - use a controller filter such as a "before filter" to require login
    - `before_action :require_login`

- Would you use Basic HTTP Authentication for authenticating users over alternatives such as the Devise gem?
  - probably not because Devise is powerful and covers a lot of edge cases and security loopholes that you might not think of

- How would you flash an error message on a user's browser if they put an invalid username?
  - in the View, use code such as `flash.now[:error] = "Invalid username!"`

- What are some reasons you would want to use the Devise gem for user authentication over building your own authorization system?
  - Devise is powerful and covers a lot of edge cases and security loopholes that you might not think of--it also allows for more advanced authentication stuff later down the Rails road