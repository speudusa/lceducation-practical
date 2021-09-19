Class Syntax
============

A class is a reusable template that creates objects.  As a template, specific syntax is required.


.. sourcecode:: js
   :linenos:

   class ClassName {

      //class properties within the constructor
      constructor(parameters) {
         this.parameter...
      }  
      //class methods can be outside the constructor
      methods {
         ...
      }
   }

Let's create a class for student grades.



``class``
---------

When defining a class, we use the keyword ``class`` then the class name in Pascal case.  
Similar to declaring a function, this keyword provides context for computer to better understand.
The entire class is contained with in ``{ }``. 

.. sourcecode:: js

   class StudentGrades {  }

``constructor``
---------------

The ``constructor`` is a very important part of the class.  
The constructor is a special method that contains all of the parameters needed to create an object.
Like a function, the constructor has opening and closing ``{ }`` that contain the class parameters.
These parameters are used to update the class properties.

.. sourcecode:: js

   class StudentGrades {
      constructor(test1, test2, test3, test4, test5){
      }

``this``
--------
When working with classes, we are creating a single instance of the class.  
The keyword ``this`` is used to let the constructor know that the arguments passed to the 
class are the ones it should use for the specific instance.  
``this`` allows all parameters passed to the constructor to remain unique, in that instance of creation.

.. sourcecode:: js

   class StudentGrades {
      constructor(test1, test2, test3, test4, test5){
      this.test1 = test1;
      this.test2 = test2;
      this.test3 = test3;
      this.test4 = test4;
      this.test5 = test5;
      }

Methods
-------
If we want the class to enact behaviors on a property or object, we create **methods** within the class.
Methods are functions specific to a class, meaning they will only apply their coded behaviors on objects of a class.  
While class methods are only accessible to properties within a class, methods are also optional in a class.

Methods Outside the ``constructor``
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Methods can be located outside of the constructor, as seen below.
This means that any object from the class has access to the class method when it is called.


.. sourcecode:: js

   class StudentGrades {
      constructor(test1, test2, test3, test4, test5){
      this.test1 = test1;
      this.test2 = test2;
      this.test3 = test3;
      this.test4 = test4;
      this.test5 = test5;
      }
      
      calcAverage(){
         let sum = this.test1 + this.test2 + this.test3 + this.test4 + this.test5;
         return sum/5;
      }
   }

   
Notice that ``calcAverage`` does not have the keyword ``function`` in front of it.

The output would look like this: 

.. sourcecode:: js

   let tamara = new StudentGrades(98, 88, 76, 98, 91);
   tamara;

   StudentGrades {
      test1: 98,
      test2: 88,
      test3: 76,
      test4: 98,
      test5: 91
   }


When we print out ``StudentGrades`` object, ``tamara``, see each test grade passed when we initialized this object.
However, there is no sign of our method.  Methods must be called in order to run.

.. sourcecode:: js

   tamara.calcAverage();

   //OUTPUT
   
   90.2


Methods Inside the ``constructor``
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

We can also have the method be part of the constructor properties. 
This is a good option if you want the method's output to be a class property, 
meaning that each object created by this constructor has the code for the method or methods.

.. sourcecode:: js

   class StudentGrades {
   constructor(test1, test2, test3, test4, test5){
         this.test1 = test1;
         this.test2 = test2;
         this.test3 = test3;
         this.test4 = test4;
         this.test5 = test5;
         this.calcAverage =   function(){
            let sum = this.test1 + this.test2 + this.test3 + this.test4 + this.test5;
            return sum/5;
         }
      }
   }


Notice that when we add a method to the properties, we use both ``this`` and ``function`` keywords.

.. sourcecode:: js

   let tamara = new StudentGrades(98, 88, 76, 98, 91);
   tamara;

   StudentGrades {
      test1: 98,
      test2: 88,
      test3: 76,
      test4: 98,
      test5: 91
      calcAverage: [Function]
   }

Why does ``calcAverage`` list ``[Function]`` and not the actual output?  We didn't actually call the method.
The method is part of the object, but like any function, it must be called in order to perform its task.

.. sourcecode:: js

   tamara.calcAverage();

   //OUTPUT
   
   90.2


``new``
--------

Recall that when we create an object from a class, we are making a new and unique object.
When declaring an object for the first time, we need to use the keyword ``new``.  
This keyword creates a new object in that moment.

.. admonition:: Tip

   Explain this code in plain English:

   .. sourcecode:: js

      let tamara = new StudentGrades(98, 88, 76, 98, 91);

   "Let the object 'tamara' be a new StudentGrades object using these values: 98, 88, 76, 98, 91."


We use ``new`` as we declare our object.

.. sourcecode:: js

   let tamara = new StudentGrades(98, 88, 76, 98, 91);

   let grant = new StudentGrades(88, 84, 79, 81, 73);

In this example, we are declaring ``tamara`` to be a ``new`` instance of ``StudentGrades``. 
Meaning that all values passed are new to the object by the name ``tamara`` and not to be confused with any other ``StudentGrades`` objects.
Pairing ``new`` with ``this`` in the ``constructor`` makes classes reusable.


.. sourcecode:: js

   tamara;

   //OUTPUT
   StudentGrades {
      test1: 98,
      test2: 88,
      test3: 76,
      test4: 98,
      test5: 91
      calcAverage: [Function]
   }

   grant;

   //OUTPUT
   StudentGrades {
      test1: 88,
      test2: 84,
      test3: 79,
      test4: 81,
      test5: 73,
      calcAverage: [Function]
   }


Accessing Properties within a Class
------------------------------------

Each instance has access to all properties and methods.
If you want to isolate one of those properties, use the following syntax:

.. sourcecode:: js

   //Syntax
   objectName.propertyName;

   //Example:

   tamara.test2

   //Output
   88







Check Your Understanding
-------------------------

Ideas:
Use different class
- ask them to predict output 


.. admonition:: Note

   I would like interactive codeblocks in the methods section - one for methods inside constructor and one for outside

   I would also like a chance to have interactive codeblocks to invite students to make their own class with at least one method.