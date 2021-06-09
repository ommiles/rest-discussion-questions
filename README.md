# REST Discussion Questions

Take 30 minutes with your table choose a *resource* that your server contains data about. A resource will be something like 'books', 'users', 'episodes', or 'characters', something that your users will be performing CRUD actions on.

1. Write out the 7 RESTful routes that correspond to the 4 CRUD actions.  Be sure to include the HTTP verb, the name of the route, the path (URL) and the corresponding CRUD action. 

   * What SQL (if applicable) would be fired in the controller actions for each of the routes?

![](https://curriculum-content.s3.amazonaws.com/web-development/rails-intro-to-rest/rails_routes.png)

| HTTP    | URL            | Route / Controller Action|CRUD   | SQL
| ------- | -------------- | ------- | ------ | -
GET       |/books          |#index    |READ    |SELECT * FROM books
GET       |/books/:id      |#show     |READ    |SELECT * FROM books WHERE id = :id LIMIT 1
GET       |/books/new      |#new      |READ    |
GET       |/books/:id/edit |#edit     |READ    |SELECT * FROM books WHERE id = :id LIMIT 1
PATCH     |/books/:id      |#update   |UPDATE  |UPDATE books SET column1 = value1, column2 = value2 WHERE id = :id
POST      |/books          |#create   |CREATE  |INSERT INTO books (column1, column2) VALUES (value1, value2)
DELETE    |/books/:id      |#destroy  |DELETE  |DELETE FROM books WHERE id = :id

`* All GET verbs / methods are CRUD Read actions.`

   * Why might it be important that routes and resources have a conventional structure?

      * Developer comms & collaboration
      * Rails macros & other magic

   * Which routes would you `render` a view and for which would you `redirect to` another route? Why?

Render is for routes based on a GET.  Other methods do not have a render associated with them, so can be redirected.

2. Let's say you have built an app that is a blogging platform. You have a Post and an Author model and you have controllers and routes for the CRUD actions of each model. You sit down at your computer and visit www.youramazingrailsblog.com/posts:

   * What kind of web request is this making? (i.e. is it a `GET`, `POST`, etc request?)

GET request.

   * What controller action (i.e. which route in which controller) will recieve that web request?

Post controller, index action.

   * What is the response that your Rails app will send back to the client, i.e. the browser?

The Rails app will send back the index page.

3. Spend a few minutes mapping out a domain model for a parking lot. How would you model the relationship between cars and spaces? How would you keep track of how long a car had been parked in a space? How would you keep track of how much money someone would need to pay for having parked a certain amount of time?

