# Learning Outcomes
- What is a WebSocket?
  - created to allow two way communication between a server and a client
  - keeps the connection between server and client open so server can send updates to the client without specific request being made

- What kinds of problems can WebSockets help you solve?
  - long-polling where allowing a client to send an http request and if there is no new info, instead of sending an empty response and closing the connection, hold the request open on the server side
  - polling where we notify users of new post and update their view, and if there aren't we just return an empty response--involved is opening and closing a request on the server still

- What is Action Cable?
  - Action Cable is a built in way to support WebSockets the Rails way
  - it handles connections; when a user has one browser tab open it will hold one connection to the Action Cable server

# Knowledge Check
- What option did developers have before WebSockets to update a client without a user request?
  - polling and long-polling

- How can you broadcast to a stream from the server?
  - set up a connection object

- Where do you broadcast to a stream from the server?
  - in `app/channels`(?)

- Where do you authorize incoming connections?
  - in `app/channels/application_cable/connection.rb`

- What are Action Cable's stream options?
  - `stream_from` and `stream_for`

- What is the difference between `stream_from` and `stream_for`
  - `stream_from` expects a string to identify the stream whereas `stream_for` operates on a model
  - use `stream_for` when you have a specific model to use the stream for