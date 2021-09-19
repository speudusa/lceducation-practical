Inheritance
============


Define/Explain inheritance
   - broad similarities => class specific traits

   Person => Employee  or => Student


.. sourcecode:: js

   class Person {
      constructor(name, age){
      this.name = name;
      this.age = age
      }

      whoAmI() {
         return `My name is ${this.name}`;
      }
   }

   class Employee extends Person{
      constructor(name, age, workPlace, yearStarted){
         super(name, age);
         this.workPlace = workPlace;
         this.yearStarted = yearStarted
      }

      whereIWork() {
         return `${this.name} started working at ${this.workPlace}  in ${this.yearStarted}`;
      }
   }

   class Student extends Person{
      constructor(name, age, school, faveSubject){
         super(name, age);
         this.school = school;
         this.faveSubject = faveSubject
      }

      whereILearn() {
         return `${this.name} goes to ${this.school} and enjoys ${this.faveSubject}`;
      }
   }

   class StudentExtracurriculars extends Student{
      constructor(name, age, school, faveSubject, extracurric){
      super(name, age, school, faveSubject);
      this.extracurric = extracurric
      }
      
      whatIDoForFun(){
         return `${this.name} is part of ${this.extracurric} group`;
      }
   }


``extends``
-----------
- Define

``super``
---------
- Define
- examples and usage

Like in other section, walkthrough steps with definitions
Would love interactive codeblocks which students could explore.


1. extends
- code with x extends y

2. super
- code with super(x, x, x)

3. student --> StudentExtracurriculars



Check Your Understanding
------------------------

ask about super - either syntax or predict


.. admonition:: Note

   As I was work through this lesson, I realized that objects need to be covered as well.  

   My plan of action would be to continue writing the classes material.  
   Once that is done, I would read through and decide where to introduce objects.   
   