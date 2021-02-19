---
layout: post
title:      "Rails MOD 3 - MyPlaylistReview"
date:       2021-02-19 15:21:13 -0500
permalink:  rails_mod_3_-_myplaylistreview
---


Rails (Module 3) is super exciting and fun.  In MyPlaylistReview app, I focused on creating, reviewing and organizing how these playlists and reviews entries (journal style) are accessed and displayed. There was loads of confusion on how I want to approach a "playlist" kind of app from the perspective of "journal-style entry" organizing -blog-ish type from looking through everyone's playlists. 

I am a visual and conditional kind of learner.  It was a lot to imagine what I need to do for this module.  I truly cannot remember all the codes.  To move efficiently, I was revisitng labs, lessions and lectures. Again, I am excited for this lab just the set up part felt windy to organize, while catching up on labs.  I appreciate that we already have some familiarity from module 2 with Sinatra. I needed to think more about the MVC, ActiveRecord, sessions and cookies, etc as I build the app. I  did not feel too lost.  Lots of googling was done, as well as referring back to the Rails documentation for all things ActiveRecord associations, helper methods, testing data and code for errors and generating migrations. 

I was careful my migrations and destroying them and googling how to generate it better. Then test the objects in the terminal. Then add create a signup form (through Sessions Controller and User controller and it's respective View pages). Of course, we will need omniauth, which was not too difficult to implement.  Basically I set up the hollow vessel first and then added the meaty part later.  Just moving the necessary omniauth. pieces (add gems, google omniauth setup, the controllers' and views' code for it, as well as writing the code for the routes) was a lot ot remember and seeing it visually in my mind. I had to write out the steps and test it out. It was easy to installed the gems, add the dotenv gems and file. Put the .env  in .gitignore and then going into the google omniauth setup.  Once the simple functions to signup , login and logout is completed, I went ahead to add the code for the controllers and the views. Then things got challenging and more focused with proper resting of my routes and codes throughout the MVC flow as I implemented the nested routes, moving repeated codes to into helpers and partials. By deciding what's necessary, as a developer, is great practice to cultivate the decision making process.

With endless testing of codes and reading errors from the terminal in VSC and the browser pages, it is an important ritual to understand why things are stuck per 'byebug' and 'pry'.   My favorite way to test objects in the very beginning of this project was through "rails c -s". This way the database is not be filled with useless data. From here I got to see what can be chained through the has_many and belongs_to through relationships. 

In this destroy action I had issues to properly destroy objects when I am not at my redirected pages.  To be redirected to the playlists index (playlists_path needed to be /playlists(.:format) to properly redirect_to once the object is destroyed.  My original attempt was putting the instance @playlist into the argument /playlists/:id(.:format) which is not what I wanted.  This is calling a destroyed show page to be redirect_to afterwards (http://localhost:3000/rails/info/routes). 
 
```    
def destroy

        @playlist = Playlist.find_by_id(params[:id]) 
        if current_user !=  @playlist.user 
            flash[:message] = "Unauthorized action."
            redirect_to playlists_path
        else
            @playlist.destroy
            redirect_to '/'
        end 
    end
```

I tried to refactored this to be skinny into methods in the private seciton. But felt it was best and clear to have it this way for the destroy method. But I was able to do so with the Review destroy method (making it skinny). 

Ultimately, it felt amazing to know that we can nest our routes and extract certain info about user, review and playlist objects to learn more about the application.  I am excited to go deeper with this process in working with database. From a socological perspective, I always find it fascsinating to understand the business logic and relationships of different entities. 

Thank you.


