# OpenClassProject8

Get started
With the todo app you are able to create, filter, and delete a list of todo items. We can see a minimalistic design, it's programmed in Vanilla javascript. The app has been creating by using the model-view-control pattern(MVC)

The MVC model divide the data logic, from the display functionality managing them with differents entity, knows as the controller.

The lead part of the program provides:

listening to user actions from View
Calling Model to perform requested operations
Calling View to display results from Model
The model view controller

Model: here we will found the generation of the methods and the creations of the prototypes that we need to manage the local storage option.
View: manages the user interactions with the application, manipulates DOM structure.
Controller: connects model and view by converting inputs from the View for the Model component.
We will use Jasmin test enviroment, to test and maintain the app. You will find all the tests in the folder ControllerSpec.js enter here the test folder.

Main files
Html
index.html
Css
index.css
base.css
Javascript
app.js
this file is the starting point to initialize the Model, View and Controller. Manage the user action listeners, delivers methods that connects View interactions with Model operations.

store.js
this file is the one that store the user last time visit todos list on the local storage but when open in another device, it will starts afresh

helper.js
deliver helper functions for DOM elements - querying, wrapping, delegating events

model.js
Data management methods

template.js
file that concern template function to display list items, change button states, escape characters

view.js
this file defines how the data will display

Bug Fixing
controller.js
bug:

Controller.prototype.adddItem
Solved:

Controller.prototype.addItem
store.js
bug:


                    for (var i = 0; i < 6; i++) {
                    newId += charset.charAt(Math.floor(Math.random() * charset.length));
                    }
                  
Solved:

var isUnique = false;

                  while (!isUnique){
                    for (var i = 0; i < 6; i++) {
                      newId += charset.charAt(Math.floor(Math.random() * charset.length));
                    }
                    isUnique = true;
                    for (var i = 0; i < todos.length; i++) {
                      if (todos[i].id == newId) {
                        isUnique = false;
                      }
                    }
                  }
                
Test
Manual testing:
Type mistake.
Location:
js/controller.js, line 95 Controller.prototype.adddItem Fixed:
Controller.prototype.addItem

Associated label to the input with a class

                    <input class="toggle-all" type="checkbox">
                    <label for="toggle-all">Mark all as complete</label>
                  
Fixed:

                    <input class="toggle-all" id="toggle-all" type="checkbox">
                  
Automatic Jasmine testing

It shoulds:
Show entries on start-up

The array has to be empty when the application start

Show active entries

shows total count of the tasks, array can be empty or filled it with the tasks

Show completed entries

when a taks is complete = false

Show the content block when todos exists

create a list of the tasks

Highlight "All" filter by default

sets 'all' as default, takes total count, even if it's empty

Toggle all todos to completed

updates all tasks as completed (model component)

Update the view

updates the status as completed (view component)

Add a new todo to the model

adds new task to the list

Remove an entry from the model

removes todo task (model component), empty array

Comparison between competitors
Design

Our todo
Minimalistic and really easy to use way. Every user able to understand can easily enjoy all the functionality of the programs without lost a considerable amounts of time reading confusional information. This helps a lot the UX.

http://todolistme.net
The design is more complex than our products. But sometimes more choice for the user means only more confusion. we see the icons on the menu "remote" and "sync" With the last we are able to create an account. Why called it sync ? and not "sing in" this could lead to several misunderstanding. About the remote, with modern technology you don't need to have 2 different version of the site, one for computer and one for mobile. And this name is wrong too.

Summary performance comparison
Evalueted Parameter	Our Todo	todolistme.net/
Loading:	          9 ms	    48 ms
Scripting	          20 ms   	1142 ms
Rendering	          6 ms	    50 ms
Painting	          2 ms	    24 ms
System	            35 ms	    224 ms
Idle	              3014 ms	   2918 ms
