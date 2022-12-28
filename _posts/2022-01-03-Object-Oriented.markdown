# Object Oriented Programming
===============

Fundamentals
------------
1. Understand ---> Analysis
2. Plan ---------> Design Object-Oriented
3. Build --------> Programming

Software Development
-------------------
Software need to be responsive, add new features and fix bugs and you
need to support continue development. Continue programming supported
by continue analysis and design. You have to use iterative approach
including analysis, design and programming to move through this steps
multiple times.

Computing Object
----------------

## Characteristics they have:

1. Identity -----> apple green or red ---> type
2. Attributes ---> name or gender -------> properties ----> class
3. Behavior -----> can run or walk ------> functions

Objects have behaviors and that behavior is specific to the type
of object.

Abstraction
-----------

Abstraction means that we focus on the essentials of something.
Abstraction means that we can have an idea or concept that it's different
from any specific instance of an object. It's what you do when you are in
conversation and it's the heart of Object Oriented, because is what you
are doing when you make a class. Ignore the irrelevant and unimportant,
a table have many other types but you know the idea of a table, the
abstraction.

Encapsulation
-------------
Show only what is absolutely necessary for the application for control
the access. Think of a black box that we close more and more the inner
working of the object, except for the feel peaces we decide to make
public for input and output. It's about reducing to dependency between
different part of the application. The idea of encapsulation is that you
enclose, you encapsulate your object attribute in methods or functions.
And you hidden everything about the object except what is absolutely
necessary to expose.

Inheritance
-----------
It's a great form of coding reuse. We can create a new class and instead
of write from scratch, we can base on an existed class.

Superclass / Parent class

Subclass / Child class

Polymorphism
------------
Polymorphism means many forms, we can overriding the method of the
superclass, this just means write the method again. Polymorphism let we
work freely with objects that we been created in any class.

Object-Oriented Analyses and Design
-----------------------------------
How to identify the classes for our application? Answer this is the
entire point of the Object-Oriented Analyses and Design. What classes
we need and what they do.

####* 1. Gather Requirements
What it the app need to do? What problem are you trying to
solve? What this app could do versus what the app can do?

####* 2. Describe The app
Describe the application, you build a simple narrative and
you plan conversation language for how people use the app.
Sometimes make a prototype of the user interface and sometimes
it's just the distraction.

####* 3. Identify The Main Objects
This is the start point for identify classes. Pick the most
important things in our application and what it's relevant.

####* 4. Describe The Interactions
Formally describe interactions between this objects and start
to understand the responsibility of the different objects. The
behaviors they need to have and when they interact with other
objects what they do? What order they need to do? When we
answer this questions, we can make a sequence diagram.

####* 5. Create A Class Diagram
Make a visual representation of the classes that we need,
we get to be really specific about Object-Oriented principles
like inheritance and polymorphism.



Gathering Requirements
---------------------------------

- ####* Functional Requirements: what does it do?
	- Features / Capabilities
>System must display the heart rate, temperature and blood
>pressure of a patient connected to the patient monitor.

>Application must allow user to search by customer's last
>name, telephone number or order number.

>Application must allow user to create 140-character message.

- ####* Non-Functional Requirements: what else:
	- Documentation / Legal / Performance / Support
>System must respond to searches within 2 seconds

>Help desk available by telephone, Mon-Fri 8am-6pm

>Be available 99.99% of time during business hours

>For more formal methodology you can use something call FURPS / FURSP+

Unified Modeling Language
-------------------------------------

- UML is a simple graphical notation specific for drawing diagrams of Object
Oriented Systems.

Example:

| BankAccount     | Operations |
| ----------------| -----------|
|  accountNumber  | open()     |
|  balance        | close()    |
|  dateOpened     | deposit()  |
|  accountType    | withdraw() |



Describe Using Cases
--------------------

###* Use Cases

**Title** - what is the goal? Short phase, active verb
>Register new member, create new page or process account.

**Actor** - who desires it?
>User, Customer, Administrator

- External System / Organizations
>External data sources, web services, other corporate
>apps, backup systems

- Roles / Security Groups
>Visitor, member, administrator, owner

**Scenario** - how is it accomplished?
>1. Customer chooses to enter the checkout process
>2. Customer is  shown a confirmation page for their order, allowing
>them to change quantities, remove items, or cancel
>3. Customer enters his/her shipping address
>4. System validates the customer address
>5. Customer selects a payment method
>6. System validates the payment details
>7. System creates an order number that can be used for tracking
>8. System displays a confirmation screen to the Customer
>9. Email is send to the Customer with order details

Extension: Describe steps for order never finalized
Precondition: Customer has added at least one item to shopping cart


###* User Story

- As a (type of user)
>As a Bank Customer
>I want to change my PIN online
>So that I don't have to go into a branch

- I want (goal)
>As a User
>I want to search by keyword
>so that I can find and read relevant articles

- So that (reason)
>As a Programmer
>I want to learn Regular Expressions
>So that I can do better substring search






CREATING A CONCEPTUAL MODEL
---------------------------

###* Identifying Objects

Start to identify possible objects on your
use case and user story.

 ```
 _________________      _________________       _________________
|                 |    |                 |     |                 |
|    Customer     |----|  Shopping Cart  |-----|     Payment     |
|_________________|    |_________________|     |_________________|
         |___________                        ___________|
                     |                      |
 _________________   |  _________________   |   _________________
|                 |  |_|                 |__|  |                 |
|      Item       |    |      Order      |     |      Email      |
|_________________|----|_________________|-----|_________________|
 _________________    __________|
|                 |  |
|     Address     |__|
|_________________|
 ```


Identifying Responsibilities
---------------------------------------

Avoid global master objects to have more responsibilities.
Responsibilities have to distribute between the objects, not in one
master object.
```
  _________________           _________________              _________________
 |                 |         |                 |            |                 |       -Verify items
 |    Customer     |---------|  Shopping Cart  |------------|     Payment     |
 |________________ |         |________________ |            |________________ |       <Provide payment and address
          |___________                                 ______________|
                      |        -Display totals        |                               >Process sale
                      |                               |
                      |                               |                               *Validate payment
                      |                               |
  _________________   |       _________________       |      _________________        #Confirm order
 |                 |  |______|                 |______|     |                 |
 |      Item       |         |      Order      |            |      Email      |       !Provide order number
 |_________________|---------|_________________|------------|_________________|
                          ____________|                                               "Check order status
<Set payment details     |                                 +Send email
*Validate payment        |     >Process order                                         +Send order details email
                         |     #Confirm order
                         |     !Get order number
                         |     "Get status
  _________________      |     +Create order confirmation email
 |                 |     |
 |     Address     |_____|
 |_________________|

<Set address details
```



Class Responsibility Collaboration
----------------------------------

CRC Cards
```
        Class name

                              |
                              |
        Responsibilities      |       Collaborators
                              |
        ...                   |       ...
                              |
                              |
```



CLASS DIAGRAM

| Product                         | Class
| ------------------------------- | -------------------------------- |
| - name: String                  | + getName(): String              |
| - isActive: Boolean             | + setActive(Boolean)             |
| - launchDate: Date              | + getProductDestails(): String   |
| - itemNumber: Integer           | + displayProduct()               |
|                                 | - formatProductDetails(): String |



Converting Class Diagrams to Code
----------------------------------------
```
                                                           _________________________________
         public class Spaceship {                         |                                 |
                                                          |             Spaceship           |
             // instance variables                        |_________________________________|
             public String name;                          |                                 |
             private int shieldStrength;                  | + name: String                  |
                                                          | - shieldStrength: Integer       |
             // constructor method                        |_________________________________|
             public Spaceship() {                         |                                 |
                 name = "Unnamed ship";                   | + fire(): String                |
                 shieldStrength = 100;                    | + resduceShields(Integer)       |
             }                                            |_________________________________|

             // overloaded constructor                    Spaceship excelsior = new Spaceship("Excelsior 2");
             public Spaceship(String n) }
                name = n;                                 Object: excelsior
                shieldStrength = 200;                      _________________________________
            }                                             |                                 |
                                                          |    name: Excelsior 2            |
             // methods                                   |    shieldStrength: 200          |
             public String fire() {                       |_________________________________|
                 return "Boom!";
             }

             public void reduceShields(int amount) {
                 shieldStrength -= amount;
             }
         }
```

Destructors / Finalizers
------------------------

Called when an object is being deleted / deallocated / released

Use for releasing resources



Inheritance Describes An "IS A" Relationship
------------------------------------------------

 A cars is a vehicle.

 A bus is a vehicle.
```
 _________________      _________________       _________________
|                 |    |                 |     |                 |
|    Customer     |----|      Bank       |-----|     Manager     |
|_________________|    |_________________|     |_________________|
         |___________                        ___________|
                     |                      |
 _________________   |  _________________   |   _________________
|                 |  |_|                 |__|  |                 |
| CheckingAccount |    |   BankAccount   |     | SavingsAccount  |
|_________________|----|_________________|-----|_________________|
 _________________    __________|
|                 |  |
|      Teller     |__|
|_________________|

                            ________________________
                           |                        |
                           |      BankAccount       |
                           |________________________|
                           |                        |
                           |  accountNumber         |
                           |  balance               |
                           |  dateOpened            |
                           |  accountType           |
                           |________________________|
                           |                        |
                           |  open()                |
                           |  close()               |
                           |  deposit()             |
                           |  withdraw()            |
                           |________________________|

                              ^        ^         ^
           ___________________|        |         |_________________
          |                            |                           |
 ________________________   ________________________   ________________________
|                        | |                        | |                        |
|     CheckingAccount    | |     SavingsAccount     | |   investimentAccount   |
|________________________| |________________________| |________________________|
|                        | |                        | |                        |
|  (has everything       | |  (has everything       | |  (has everything       |
|  from BankAccount)     | |  from BankAccount)     | |  from BankAccount)     |
|                        | |                        | |  accountRep            |
|  lastCheckNum          | |  interestRate          | |  withdraw()            | overriding
|________________________| |________________________| |________________________|


                            ________________________
                           |                        |
                           |        Product         |
                           |________________________|
                           |                        |
                           |  title                 |
                           |  price                 |
                           |________________________|
                           |                        |
                           |  purchase()            |
                           |  download()            |
                           |________________________|

                              ^        ^         ^
           ___________________|        |         |_________________
          |                            |                           |
 ________________________   ________________________   ________________________
|                        | |                        | |                        |
|        Album           | |         Book           | |         Movie          |
|________________________| |________________________| |________________________|
|                        | |                        | |                        |
|                        | |                        | |                        |
|  artist                | |  author                | |  director              |
|                        | |                        | |                        |
|                        | |                        | |                        |
|________________________| |________________________| |________________________|
```


Calling A Method In The Super / Parent / Base Class
---------------------------------------------------

Java    `Super.doSomething();`

C*    `Base.doSomething();`

VB.NET    `MyBase.doSomething()`

Ruby    `super do_something`

Objective-C    `[super someMethod];`

C++     `NamedBaseClass::doSomething();`


Abstract Classes
----------------

Bank Account can be considered an abstract class,
because it's exists purely for been inherited.
Abstract classes are never instantiated and it's
incredible useful, can contain functionality,
methods, variables and so on. Because it all be
inherited, so it exists to provide sharing behaviors.

```
                                   ________________________
                                  |                        |
                                  |      BankAccount       |
                                  |________________________|
                                  |                        |
                                  |  accountNumber         |
                                  |  balance               |
                                  |  dateOpened            |
                                  |  accountType           |
                                  |________________________|
                                  |                        |
                                  |  open()                |
                                  |  close()               |
                                  |  deposit()             |
                                  |  withdraw()            |
                                  |________________________|

                                     ^        ^         ^
                  ___________________|        |         |_________________
                 |                            |                           |
        ________________________   ________________________   ________________________
       |                        | |                        | |                        |
       |     CheckingAccount    | |     SavingsAccount     | |   investimentAccount   |
       |________________________| |________________________| |________________________|
       |                        | |                        | |                        |
       |  (has everything       | |  (has everything       | |  (has everything       |
       |  from BankAccount)     | |  from BankAccount)     | |  from BankAccount)     |
       |                        | |                        | |  accountRep            |
       |  lastCheckNum          | |  interestRate          | |  withdraw()            |
       |________________________| |________________________| |________________________|
```


Interface Classes
-----------------

>"Program to an interface, not an implementation." Design Patterns, 1995

It's recommended that you become familiar, with the idea of the
interface in your chosen language. Because they often have many
features friendly than use inheritance.

###* Defining interface Contract
```java
interface Printable {

	// method signature
	void print();
	void printToPDF(String filename);
}
```

###* Implement Interfaces
```java
class Myclass implements Printable {

	// method bodies
	public void print() {
		// provide implementation
	}

	public void printToPDF(String filename) {
		// provide implementation
	}

	// addition functionality...

}
```

##* Using Interface
```java
// sometime later
while (genericObject in listOfObjects) {

	if (genericObject instanceOf Printable) {
			// if it emplements the interface, we can use it
			genericObject.print();
	}
}
```

Aggregation Describes A "HAS A" Relationship
--------------------------------------------
###* Aggregation And Composition
```
        _________________               _________________
       |                 |             |                 |
       |    Classroom    |<>-----------|     Student     |
       |_________________|1           *|_________________|

                           aggregation

        _________________               _________________
       |                 |             |                 |
       |    Document     |<>-----------|       Page      |
       |_________________|1        1..*|_________________|

                           composition
                        implies ownership
```


###* Creating Sequence Diagrams
```
        _________________                    _________________                    _________________
       |                 |                  |                 |                  |                 |
       |   a Customer    |                  | a Cart:Shopping |                  |     :Order      |
       |_________________|                  |_________________|                  |_________________|
                |                                    |                                    |
                |                                    |                                    |
                |             checkout               |                                    |
                |___________________________________\|                                    |
                |                                   /|         createNewOrder             |
                |                                    |___________________________________\|
                |                         ___________|___________________________________/|_________
                |                        |    |      |                                    |         |
                |                        |Loop| all  |     addItem(item, quantity)       _|_        |
                |                        |____| items|--------------------------------->|   |       |
                |                        |           |                                  |   |       |
                |                        |           |            itemtotal             |   |       |
                |                        |           |<---------------------------------|_ _|       |
                |                        |___________|____________________________________|_________|
                |                                    |                                    |
                |                                    |       calculateDiscount           _|_
                |                                    |_________________________________\|   |
                |                                    |                                 /|   |
                |                                    |         finalizeSale             |   |
                |                                    |_________________________________\|   |
                |                                    |                                 /|   |
                |                                    |              total               |   |
                |<-----------------------------------|----------------------------------|_ _|       _________________
                |                                    |                                    |        |                 |
                |               sumbitPayment        |                                    |        |     Payment     |
                |____________________________________|___________________________________\|        |_________________|
                |                                    |                                   /|                 |
                |                                    |                                    |  createPayment  |
                |                                    |                                    |________________\|
                |                                    |                                    |                /|
                |                                    |                                    |     results     |
                |                                    |                                    |<----------------|
                |                                    |                                    |                 x
```



UML Diagrams
------------

```
        Class Diagram                          Example of State Machine Diagram:
        Use Case Diagram
        Object Diagram                                             flip switch
        sequence Diagram                                          _____________
        State Machine Diagram                  _________________ /             \ _________________
        Activity Diagram                      |                 |               |                 |
        Deployment Diagram                    |  lamp off       |               |    lamp on      |
        Package Diagram                       |_________________|               |_________________|
        Component Diagram                                        \_____________/
        Profile Diagram
        Communication Diagram                                      flip switch
        Timing Diagram
        Composite Structure Diagram
        Interaction Overview Diagram
```



DESIGN PATTERNS
---------------
From the book Design Patterns - Elements of Reusable Object-Oriented Software.
Design Patterns is a well tested solutions for common problems we each use in
Software development. Think like best practice, suggestions for how you may
arrange your classes and objects to accomplish result. This book describe 13
design patterns, we have to split in tree groups.

| Creational Patterns   | Structural Pattern  | Behavioral Patterns     |
| ----------------------|---------------------|-------------------------|
| Abstract Factory      | Adapter             | Chain of responsibility |
| Build                 | bridge              | Command                 |
| Factory Method        | Composite           | Interpreter             |
| Prototype             | Decorator           | Iterator                |
| Singleton             | Facade              | Mediator                |
|                       | Flyweight           | Memento                 |
|                       | Proxy               | Observer                |
|                       |                     | State                   |
|                       |                     | Strategy                |
|                       |                     | Template Method         |
|                       |                     | Visitor                 |


Singleton
---------

###* Implementing A Singleton In Java


```java
public class Mysingleton {

    // placeholder for current singleton object
    private static MySingleton __me = null;

    // private constructor - now no other object can instantiate
    private MySingleton() { }

    // this is how you ask for the singleton
    public static MySingleton getInstance() {
        // do I exist?
        if ( __me == null ) {
            // if not, instantiate and store
            __me = new MySingleton();
        }

        return MySingleton;

    public someMethod() { //... }

}
```

###* Using A Singleton In Java


```java
// ask for the singleton
MySingleton single = MySingleton.getInstance();

// use it
single.someMethod();

// or even just call directly
MySingleton.getInstance().someMethod();
```

Memento
-------
>Handles "undo" in an object

>Does not violate encapsulation

General Software Development Principles
--------------------------------------
- DRY: Don't Repeat Yourself

- YAGNI: You Ain't Gonna Need It
Solve the problems that you know exists,
don't write speculative code. Solve today's
problems.

###* Examples Code Smells

Unnecessary code or duplicate code, we sometimes refer to are Code Smells like:

- Long methods

- Very short (or long) identifiers(variables)

- Pointless (or long) comments

- God object (to many tasks)

- Feature envy


Solid Principles Of Object-Oriented Design
------------------------------------------


- S : Single Responsibility Principle

        An object should have one reason to exist,
        one reason to change - one primary responsibility

- O : Open / Closed Principle

        Open for extension, but closed to modification.
        If you write working code and them you requirement
        change, if you need to add behavior. You do it by
        writing new code, not by change all the code that
        already works. One example is Inheritance.

- L : Liskov Substitution Principle

        Derived classes must be substitutable for their base
        classes. Means that if we created a hole bunch of
        child classes, I should always be able to pass any
        of these around and treat then like the super class.
        If a child can't be treat as super class, you don't
        have a super class.

- I : Interface Segregation Principle

        Multiple specific interfaces are better than one
        general purpose interface.

- D : Dependency Inversion Principle

        Depend on abstractions, not on concretions.

        Abstract methods between the objects, to make your
        code mode reusable. Allows substitutions and flexibility
        going forward.

                                          _________________
                don't do                 |                 |
                                         |      Store      | Object
                                         |_________________|
                                       _______ |      |_______
                                      |                       |
                                      |                       |
                                      |                       |
                                      |                       |
                               ______ |_________      _______ |________
                              |                 |    |                 |
                              | AudioFileReader |    | AudioFileWriter | Concretions
                              |_________________|    |_________________|




                                          _________________
                what you should do       |                 |
                                         |      Store      | Object
                                         |_________________|
                                       _______ |      | ______
                                      |                       |
                                      |                       |
                                      |                       |
                               ______ |_________      ________| _______
                              |                 |    |                 | Abstractions
                   __________ |      Reader     |    |      Writer     |__________
                  |           |_________________|    |_________________|          |
                  |                   |                        |                  |
          _______ |________    ______ |_________      ________ |_______   _______ |________
         |                 |  |                 |    |                 | |                 |
         | MovieFileReader |  | AudioFileReader |    | AudioFileWriter | | MovieFileWriter | Concretions
         |_________________|  |_________________|    |_________________| |_________________|




GRASP PRINCIPLES OF OBJECT-ORIENTED DESIGN
------------------------------------------

GRASP have a responsibility focus. Who creates this object?

###* General Responsibility Assignment Software Patterns

- Creator
```
Who is responsible for creating an object?
Which object is responsible for create another objects?

            _________________               _________________
           |                 |             |                 |
           |    Document     |<>-----------|       Page      |
           |_________________|             |_________________|

```
- Controller
```
Don't connect UI elements directly to business objects

                (problem: high coupling, low cohesion)

                     _________________                             _________________
         Don't do   |                 |                           | User Interface  |
                    | Business Object |<------------------------->|     Object      |
                    |_________________|                           |_________________|


                     _________________      _________________      _________________
         What you   |                 |    |                 |    | User Interface  |
         should do  | Business Object |<-->| Controller Obj  |<-->|     Object      | Model View Controller MVC
                    |_________________|    |_________________|    |_________________|
```
- Pure Fabrication
	- When the behavior does not belong anywhere else,
	create a new class. Force behavior for to an
	existence class, will decreasing cohesion. We
	instead invent, we fabricate a new class.



- Information Expert

	- Assign the responsibility to the class that has the information needed to fulfill it

```
            There nothing that could stop us for calculating the
            total items and store in the customer object, but if
            you think about it. It's the shopping cart that knows
            the most of the all items inside. It's shopping cart
            that should to be responsible for that.
             _________________    _________________    _________________
            |                 |  |                 |  |                 |
            |    Customer     |  | Shopping Cart   |  |      Item       |
            |_________________|  |_________________|  |_________________|

```
- Indirection

	- To reduce coupling, introduce an intermediate object

```
                                            _________________
         Don't do                          |                 |
                                           | Business Object |
                                           |_________________|
                                             |   |    |    |
                     _________________       |   |    |    |       _________________
                    |                 |______|   |    |    |______| User Interface  |
                    | Business Object |__________|____|___________|     Object      |
                    |_________________|______    |    |     ______|_________________|
                                             |   |    |    |
                                             |   |    |    |
                                             |__ |___ |___ |_
                                           |                 |
                                           | Business Object |
                                           |_________________|


                                            _________________
         What you should do                |                 |
                                           | Business Object |
                                           |_________________|
                                                    |
                     _________________      _______ |________      _________________
                    |                 |    |                 |    | User Interface  |
                    | Business Object |----| Indirection Obj |----|     Object      |
                    |_________________|    |_________________|    |_________________|
                                                    |
                                            _______ |________
                                           |                 |
                                           | Business Object |
                                           |_________________|
```

- Low Coupling / High Cohesion

	- Coupling: the level of dependencies between objects

                If your object have to connect to other five
                object and need to call, twenty method just
                to work. You have high coupling, lots of
                dependencies have lots of chances to break
                your code if you make changes.

	- Cohesion: the level that a class contains focused, related behaviors to the responsibility.

                If a god object have multiple behaviors and
                all of each have nothing to do with each other.
                You have Low Cohesion.

        The aim is LOW COUPLING & HIGH COHESION

- Polymorphism

	- Automatically correct behavior based on type
                We don't want to do conditional logic that check
                for particular types. We want to work with polymorphic.
                Which means, we think about inheritance, we think about
                a class design.





- Protected Variations
	- Protect the system form changes and variations

                Identify the most likely points of change

                Use multiple techniques: encapsulation, LSP, OCP
