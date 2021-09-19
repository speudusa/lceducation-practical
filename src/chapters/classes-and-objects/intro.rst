What are Classes and Objects
============================

.. index:: ! class, ! object

A Real Life Example
-------------------

Think of a video game where you can create one or more characters to play as.
When you are creating a character, you might be asked to select elements such as hair color or shoes.
Once you select your elements, you have created your very own unique character.
The properties, hair color and shoes, might become arguments for functions that will add behavior to these particular elements.
For example, hair color is a visual element to identify your character, 
but shoes can add to character stats.
Combine these elements and you have a unique character for your game.



Classes Keep Things In Order
----------------------------

If you were to code your character using your current skills, you might have something that looks like this:

.. sourcecode:: js

   let playerHair = "red";
   let playerShoes="ballet slippers";
   let playerJump = 2;
   //... pants, eyecolor, length of hair, or even style, etc.

   function playerJump(){
      if (this.shoes == "ballet slippers"){
      return 5;
      }
      //... etc for other options...
   }

   shoeSpecs(playerShoes);

   //This is a very small part of code, and for one player.  


This could work, but what if you wanted more than one player?  
You would have to duplicate all your code and update your variable names to reflect that every variable is for a separate character.
That could get tedious, long, and easily buggy.

This is where a **class** would be very useful.  
Classes are reusable blocks of code that group **properties** and **behaviors** to create unique **objects**.
Objects are the unique output of this combined data and designated their own memory space. 
No two objects are the same, even if passed identical values.  More on that later.

Class properties refer to data required by the class, and class behaviors refer to any methods contained within the class. 
In short, classes are reusable templates that allow you to create multiple objects while keeping your code DRY.

If we were to make our character above using a class, it would look like this:

.. sourcecode:: js

   class PlayerBuild {

   constructor(hair, shoes){
      this.hair = hair;
      this.shoes = shoes;
   }
      playerJump(){
      if (this.shoes == "ballet slippers"){
      return 5;
      }
      //... etc for other options...
      }
   }


   let player1 = new PlayerBuild("red", "ballet slippers");
   let player2 = new PlayerBuild("green", "steel toed boots");
   let player3 = new PlayerBuild("black", "bare feet");


Do you see how much easier it is to create a character for ``player1``, ``player2``, and ``player3``?
We were able to create them in a single line of code thanks to the ``PlayerBuild`` class.


In the next section, we will break down the syntax so that you can create classes of your own.


Check Your Understanding
------------------------

T/F Classes are reusable blocks of code 
   T


.. admonition:: Note

   If more time, I would make these codeblocks interactive


