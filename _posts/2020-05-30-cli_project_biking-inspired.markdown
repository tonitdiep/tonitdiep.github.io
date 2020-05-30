---
layout: post
title:      "CLI Project: Biking-Inspired  "
date:       2020-05-30 10:03:50 +0000
permalink:  cli_project_biking-inspired
---


***Tackling my first CLI Project*** by Toni Diep

In this CLI project, I am accessing the url’s data from an API, to build the class API. With such data, about biking with Citi Bikes in New York City, that drives the user’s experiences with the application.  To unpack the data types I am working with from the API, that I parsed with JSON, to determine my first variable called `“array_of_stations” =  hash[“network”][“stations”]`. 

I decided to only focus on the elements of: name (the bike stations in address form); empty_slots (parking spots available); and free_bikes (the availability of bikes), all based on the chosen and/or current location. Both empty_slots and free_bikes are integers, so I converted the them into strings, using: **.to_s** in `display_station_details(stations`) method.

Next, I determined a specific range of stations to build my CLI from, for a more focused project, despite the growing indexes of bikes’ stations.  How did I do this in class API? To access an array of stations, at indexed range [0..100], with iteration in the each method within the do/end block, with *“stationhash*” as my placeholder, between the pipes, || to indicate the purpose of this instance method.
`	array_of_stations[0..100].each do |station_hash|`

Learning to operate from a test-driven development, by graciously plugging in **‘binding .pry’**, between the lines of codes and their respective blocks, to check for errors and reveal inputs and outputs, all in the grandness to zero errors, with an operating CLI. Learning about the user’s input and output, in alignment with the data, also assists in the validation and invalidation of the return values from the user’s experiences. This became super important in  `“ask_user_for_bike_choice”` method, involving the until loop, that keeps on looping, until the user’s reached a valid selection. The invalid selection, prompts that user’s attention of the invalidation, along with the specific range of selection, before the user decides that it’s done.

In this next instance method “`display_station_details(station_instance)`, so we can keep the separation of focus in the CLI concise and clutter-free, and will display the complete details of the station for the user to access. Now the application ends with **“Goodbye”**. Furthermore, I remember, endless, **“.pry”** testings, to build the groundwork, logic-wise to achieve a more interactive application, that’s accessible for the users.  

For fortification purposes, I put a timer to update and push my work to GitHub from the terminal, I ran the following three lines, between 15 mins to 30 mins increments:
1. “git add .” 
1. “git commit -m “input name that reflect what is saved on””
1. “git push”

Most importantly, this is my first development project at Flatiron, from the culmination of about three week(ish) of coding and hard-learning. I am super thrilled to continue cultivating my knowledge and practice in software engineering.  My last biking experience was in California.  Eventually, I will manifest my first biking experience in NYC, sometime this year, or 2021.  With quarantining since late March 2020, I am missing the outdoors and sunshine in this wild normal..until then, happy coding, wherever we are.




