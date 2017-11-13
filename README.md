# CSMaterialTable
A Material Table App for backyard workworking projects to help determine just how much wood I would need to buy.  

I had just finished a woodworking project where I build my grandkids a picnic table. I found the plans for a
childs picnic table on pinterest which outlined the cuts and assembly. For me, the first step of any workworking
project is to compile a list of cuts, then organize those such that I minimzed the waste and amount of wood I need to buy.  

It wasn't until after I had the table together, I readlized just how small it was.  Ok for now, since the grandkids
are 2 and 4 years old.  But next year might not be so. So, found myself wishing I'd made the table a wee bit bigger.  

While re-thinking the project, I found myself wishing I had an app to do all this for me, and the idea for the Material
Table App was born.  

I decided to do this one in C#. I've been doing alot of Java lately and decided I needed to knock the rust off my C#
skills. Back when I was doing C# for the Solid Edge Mobile Viewer, data binding was the hardest nut for met to crack.
I'll try to use that as much as possible.  

The next two sections are requirements and detailed requirements.  I'll probably add, remove and/or modify these items
as I go along, al la agile.  After that will be my implementation diary.  For each day, I list task I may work on.  If
complete one, I'll strike it out and leave it under that date. If incomplete, the next day, I'll create a date header
and move those to that day.  Looking back, for a given day, you'll only see what was completed on that day.

FYI: Anywhere I use the word 'cut', I'm talking about a single piece of wood, cut to length, that is one item of the project.

### Requirements
* A '+' button by which a new cut can be added to the project
* The display will show a list of cuts, growing as cuts are added.
* Each cut will have a length and name
* The display will show a purchase list.
* As cuts are added to the cut list, will be organized and the purchase list will update.
* The purchase list will show each board and which cut to make from that board.
* After all cuts have been entered, the purchase list will show the minimum number of boards with minimal waste.  

### Detailed Requirements
* Option to print the material table
* Options to save and load material tables
* Option to select the length of the board from which cuts will be made. Ex. 8', 10' or 12'
* Scale factor.  The idea is, I would enter the cut length directly from the Pinterest plans. Then, if I wanted to make
the project bigger, rather than re-enter all the cuts, change the scale factor from 1 to, say, 1.3 (for 30% bigger) and
the cut lengths and purchase list would automatically update.
* Price and description.  In addition to specifying the length of the board from which to make the cuts, I could also
supply the price and a description for that board. Ex.  A 1x8 Presure Treated Deck Board at The Home Depot is $4.62.
If the app determines that I need 5 boards, it would tell me $23.10, times sales tax (9% currently) for a total cost of $25.18.
* Non-wood items.  The app will have a third table for things like screws, sandpaper, etc.  For each item, I would enter
a price and description.  The cost for these items would be added to the cost of the wood, giving a cost for the entire project. 
* item in the purchase list, each item will have the appearance of a board, sectioned to each item to be cut from it.  The 
section will be sized to represent the length of the cut and will contained the name of the cut, centered.  If the name is
too long for the section put the name off the board with arrows pointing to the secton.

### 11/13/2017
* Create java app with a display and control panel
* define a module for one item in the cut list.
* create controls on the display for defining a new cut item. Length in inches, and name, such as "leg #1".
* add the new cut item to an observable list (If I remember, I'll need an observable list in order to bind it to a controls
on the display)
* create a controls on the display for the cut list
  * '+' button for creating a new cut item.
  * pressing the '+' button will start the functionality for creating a new cut item.
  * text controls for inputting the cut item length and name
  * list conttro for displaying the cut list
  * 'x' button for each item in the cut list to remove the item from the list.
* Button and functionality for saving the items in the cut list
* Button and functionality for loading cut items and adding them to the cut list.  Need to do this early in the implementation
because I don't want to have to keyin a cut list every time I run a test