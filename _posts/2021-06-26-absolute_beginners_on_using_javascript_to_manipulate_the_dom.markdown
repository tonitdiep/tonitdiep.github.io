---
layout: post
title:      "Absolute Beginner's: On Using JavaScript to Manipulate the DOM"
date:       2021-06-26 05:35:13 +0000
permalink:  absolute_beginners_on_using_javascript_to_manipulate_the_dom
---


Here is a document object (image) that serves as the very foundation of what we need to do with the Document Object Model (DOM ) using JavaScript(JS) as web developers. There is an array of resources on the web on JS, HTML, and DOM from w3schools.com to https://developer.mozilla.org/.
The first node in this tree or document object starts at the 'html' is the root element is the child of the document object. The next siblings' relationship is between 'head' and 'body', as they both are also children of the 'html'.
A bit further down the tree, there is 'head' with the child of 'title' and so on. Knowing these elements is vital in manipulating the DOM with ease. Here are some of the many methods to access any trees of nodes: 
<.getElementById()>, <.querySelector()>, <.querySelectorAll()>.
document object. image: https://www.w3schools.com/js/js_htmldom.aspThese methods are utilized to extract specific data or object to be manipulated onto a DOM. Ultimately, the functionality and interactive experiences on the frontend for clients is vast from clicking a 'like button' to displaying filtered objects at various perspective as well as updating content with of something without refreshing the page.
The perspective by Chibuike Okere's on JS DOM manipulation by understanding its nodes is duly appreciated. The link is provided below.
In summary:
Simply, understanding how to traverse or navigate the document means we are becoming exquisite in dealing with nodes and their parent(s), child(ren and sibling(s). For instance, we have a tree of:
parentNode, childrenNodes, firstElementChild, lastElementChild, nextElementSibling, previousElementSibling

Okere's describes this in the following ways:
Every node has exactly one parent, except the top node (which has no parent).
A node can have more than one child.
Siblings (brothers or sisters) are nodes with the same parent.

Most importantly, working with JavaScript also means entirely engaging with HTML elements and attributes and CSS styles on these pages.
This is a reflective snippet on JS and the DOM. For those needing a digestible perspective about JS and DOM manipulation before googling and diving deep into these subjects. Having completed my first JS project, I am now more excited to build mini-projects to cultivate these JS, CSS, DOM skills as well as working with API.
References:
https://www.freecodecamp.org/news/how-to-manipulate-the-dom-beginners-guide/
w3schools.com
https://developer.mozilla.org/.
