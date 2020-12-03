---
layout: post
title:      "S i n a t r a - Blog App"
date:       2020-12-03 04:39:22 -0500
permalink:  s_i_n_a_t_r_a_-_blog_app
---



Sinatra is a Domain Specific Language used in Ruby to write web applications that is quick and simple and still powerful created by Blake Mizerany. Sinatra is also a Rack-based kind of application that also works well with Rails. <a href=”https://learn.co/tracks/online-software-engineering-structured/sinatra/sinatra-basics/what-is-sinatra”> a tiny more about Sinatra</a>

Upon a user’s requests, it is exciting to see how the 7 Sinatra RESTful Routes functions by Create, Read, Update and Destroy to understand the two assocations between Models User and Blog classes associations: 
* that a user has_many blogs
* that blogs belongs_to a user. 
* In the Models User class, holds the implementation of validations and "has_secure_password" from ActiveRecord to make sure there is only proper '/signup' and '/login'. 

For my '/signup' route I am validating that the input fields of name[username] and name[password] are entered correctly and cannot be emptied. 

Otherwise an error message will appeared. 

In ActiveRecord the "has_secure_password" macro makes sure that the presence of a password is true and entered into its form filed. This way,  we can remove this line of code `validates: password, presence: true`. We do not need this! "has_secure_password" already takes care of this check!

Furthermore, "has_secure_password" automatically performs these reponsbilities<a href=”https://api.rubyonrails.org/v5.2/classes/ActiveModel/SecurePassword/ClassMethods.html#method-i-has_secure_password”>has_secure_password documentation</a>: 
1.  “true” must hold “presence” for entering a password
2.  checks that password length is less than or equal to 72 bytes
3.  Confirmation of password (using the “password_confrimation attribute)

This is all happening behind the scenes in the Model side:
Sinatra's Model, a Ruby class that inherits from ActiveRecord::Base in `class User < ActiveRecord::Base`.

To '/signup' we want to make sure that we do not accept duplicates of the same username. This line of code checks this off:

``` validates :username, presence: true, uniqueness: true``` 

Also I do not have to separate the validation of for username's presense and uniquness, as they can be combined to validate to true. Here it is again: 

``` validates :username, presence: true, uniqueness: true``` 

Now we must all notice that the HTTP verb (& RESTfl routes) requests is taking place in the users_controller.rb on of many controllers, that is the C for Controllers in  MVC. Sinatra's Controller, a Ruby class that inherits from Sinatra::Base in `class UsersController < ApplicationController`. 

From the get '/' root is displayed from views/welcome.erb page taking us onto the browser view. These links in [Signup],  [Login], [Logout]  is located on the top left corner of all the web pages. In written code,  I have these clickable links setup in a conditional statements in the Ruby erb tags saying: 

* with the use of this helper method, if the user "is_logged_in? this would be the current_user.username with their name displayed as they have the option to [Logout] when they are done with their browsing session. 
* ELSE, the [Login] and [Signup] links are available to ensure all users can signup and login to write and save their blogs. 

```
        <% if is_logged_in? %>
          <i><%= current_user.username %></i>
          <a href='/logout'>Logout</a>
        <% else %>
          <a href='/login'>Login</a>
          <a href='/signup'>Signup</a> 
              
        <% end %>  
```
Once the user clicked the [Signup] link we are then taken to the post '/signup' route (from the controllers) to instantiate this new user signup to also pulls the form field inputs from the views/users/signup.erb for the user on the web browser perspective to enter their info (username and

```     user = User.new(username: params[:username], password: params[:password])```


In the web browswer perspective, between the signup.erb and  the users_controller.rb, also goes through the conditional statements and use of params to instantiate a new user, first before saving it to the database.


I have implemented the use of error messages in the post '/signup' action in the users_controller.rb and flash[:message] in the signup.erb when the user are not successfully entering the correctly and elgible signup information. 

These specific error messages appeared upon the signup URL (in the browser), based on: 

* if the input of the username is already taken: "Username has already been taken"

* if password field is emptied;
```Password can't be blank```

* if username field emptied:
```Username can't be blank```

Once the signup params input form fields of name[username] and name[password] area successfully entered, then the "Submit" button is pressed.  This new user is redirected to a new URL route, of '/blogs' (index page) on the browser. This new user can read other users' blogs and create their blog to submit. OTHERWISE, this user will be redirected back to the same '/signup' route to try again with the signup authentication processes.

Referencing Sinatra RESTful Routes in this overview makes a user-friendly view to not get stuck with writing codes in the controllers plus their CRUD functionalities. 

I am reminded that I can use the URL routes to access specific params through using the MVC,  building frameworks to build web apps. Specificially ensuring the "separation of concerns" principles is used to group files, accomplish certain tasks between the MVC interactions that is also uniquely defined.

| HTTP VERB  | ROUTE  | Action | Usage |
| -------- | -------- | -------- | --------|
| GET     | '/blogs'      | index action     | index page to display all blogs |
|| GET     | '/blogs/new'      | new action     | displays create blog form |
| POST     | '/blogs'      | create action     | creates one blog |
| GET     | '/blogs/:id'      | show action     | idisplays one blog based on ID in the url |
| GET     | '/blogs/:id/edit'      | edit action     | displays edit form based on ID in the url |
| PATCH     | '/blogs/:id'      | update action     | modifies an existing blog based on  ID in the url |
| PUT     | '/blogs/:id'      | update action     | replaces an existing article based on ID in the url |
| DELETE     | '/blogs/:id'      | delete action   | deletes one blog based on ID in the url |

Lastly, thes are awesome Ruby gems to work with: "shotugn" and "binding.pry" to check what's happening in the params, as well as "tux' to see persisted objects hitting the database. Although these gems can feel overwhelming, they effectively show what is happening to my CRUD functionality and params between the MVC paradigms.

