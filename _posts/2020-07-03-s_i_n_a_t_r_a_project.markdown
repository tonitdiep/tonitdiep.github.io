---
layout: post
title:      "S I N A T R A Project"
date:       2020-07-03 00:22:07 -0400
permalink:  s_i_n_a_t_r_a_project
---


A Bird’s-Eye View: My First Sinatra Project’s Learning Discoveries: 

Immediately, visually draft your RESTful routes to understand Sinatra project might look like or simply go down each HTTP verb to determine user’s access from get’/’ page to the signup/login to the webapp experience to logout is brief overview of how my Sinatra Project developed, with the challenges and focus points to ask myself from start to finish: 
1. How’s the logic and redirects and routes using CRUD?
2. What’s the has_many and belongs_to relationship in this webapp? 
3. When do unique validations occur? 
4. What are other ways to validate the user’s experience here? If statement? ternary operator? session_secret? 

This project process is intense and long, being my first sinatra project, but with the support and assistance of my peers and cohort lead, I am super grateful to understand how ruby gems are used in Sinatra, and most importantly experiencing the challenges and questions to solutions/output, as a web developer. 

Knowing how to access the “separation of concerns” from Models, Views and Controllers (MVC), is key to filing the files and folders for direct access from various controllers and views to embed the html forms. Used “shotgun” to test my codes in the url browser. Add the “binding.pry” to check the params and return values for the user_id and product.id, and for connectivity and functionality in these RESTful routes. 

About those "helper methods": 
What are helper methods? Are simple blocks of codes, that can be reused with less written lines of code through the entire webapp programming!! (major like!) 

For example, a successful “logged_in?” includes: uniqueness and validation of username, along with password and email to complete the signup process. In my signup process, “required” are embedded like so: 


```
<h1> Signup Page </h1>
<form action='/users/signup' method="POST">
   Username: <input type="text" name="username"required>
   Password: <input type="password" name="password" required>
   Email: <input type="text" name="email"required>
   <input type="submit" value="Create">
</form>
```


..So now, here are different checks into order to become a user aka contributor in this skincare product review:

These are  that validated the user’s logged_in is a flash[:message] vaguely alerting them with, “Invalid Username or Password”. Otherwise, the Signup fields are available with “required” (acting as alert flags), embedded into the erb :’‘/ users/signup’ to make sure a new user completely fill out a username, password, and email to complete their signup process.

Back to the “helpers method” first plugged into the application_controller.rb, as a main channel to connect my methods to the use_controller.rb to drive a successful “logged_in?” Next page, is the erb :’/products/index’ page is a list of all reviewed products. A User can click and view these products, as well as contribute there opinion about their product experiences. However, they are not given access to edit and delete those products that is reviewed on. To contribute their skincare product reviews from attributes on the product’s description, rating, price and reorder which is built into the User’s review submission on the ‘/products’ (erb :index) page. A new user must signup or “current_user” is required to login to review these products  and contribute their product reviews.

From this bird’s-eye view: the user’s session with their login or signup credentials, is given/access through enabling and setting the session_secret, this process is fortified with ENV[‘SESSION_SECRET’] until they press the “log out” button to end their webapp session. In the models/user.rb, the User’s class contains the “has_secure_password” to “authenticate” passwords and encrypt (install the BCrypt gem). HERE, unique validations are done to when creating that username, along with the email, upon a new user sign up.


Furthermore, getting the logic behind the RESTful routes appropriately to create, read, update and delete, truly locked in the has_many and belongs_to relationships between a user and their products. Then the rest of the logic into the “redirects” from adding a new product, logging in and out to signing up and viewing the index of products makes sense. Again, a user has_many products, while products belongs_to a user. This is seen on the aspect if the user would reorder such products, so this attribute, set to a boolean (false/true). From here, the buttons I created for the users are “yes” for true and “no” false, in the backend (w/ the booleans) and the “yes/no” at the client user side (frontend). 

Thank you for taking the instance to learn about my Sinatra project and experience building any webapp. I am excited to practice more on Ruby gems, like Sinatra, and stylings through html and css, to become a dynamic full stack developer. Thank you cohort team! -Toni Diep
 




