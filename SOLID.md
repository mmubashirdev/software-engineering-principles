SOLID Principle in OOP.

Writing code isn't just about making it work. It's about making it easy to maintain, extend, and understand.

S: Single Responsibility Principle

A class should have one clear responsibility. Small classes are easier to maintain and less likely to break when changes are made.

For example:

In a teaching application a student class can take all the functionality for the student into a class but this breaks single responsibility principle. Student class is responsible for storing student details, saving them to the database, sending emails and enrolling in courses so here we have many reasons we would need to refactor code and there are multiple ways that bugs could be introduce. Also multiple developers working on same features end up in  merge conflicts.

Fix:

Make separate classes out of Student class for each responsibility but don't take it too far!


O: Open Closed Principle
Code should be open for extension but closed for modification. Instead of changing existing code, design it so new functionality can be added without affecting already working code. To achieve this we create a new class that works on the same interface as original class we can then call the new method without affecting the original method in our application.

L: Liskov Substitution Principle
A child class should be able to replace its parent without changing the behavior of the application. 

For example: 

Suppose there is a child class  that is able to do everything that a parent class can do. A parent class might be able to do things such as eat, sleep, go to work and make dinner then we have a child class that is inherited from that parent class now obviously a kid can't make dinner and go to work 😅. This would break substitution principle because we can't use the child for such tasks.

Fix:

Create a human class and then have an adult and a child class that would inherit from human class

I: Interface Segregation Principle
Avoid large interfaces(rules). It's better to create smaller, focused interfaces so classes only implement what they actually need.

To overcome this split the methods into different interfaces based on groups If you need all at once create a main interface that nherits from all others interfaces 

D: Dependency Inversion Principle
It states that high level modules shouldn't depend on low level modules they should both depend on an abstraction This reduces tight coupling and makes applications easier to test, maintain, and scale.

For example:

There is a service class and that save something to a database for this you could create an instance of repository class directly inside service class but now a high level module is dependent on a lower level module

Fix:
Create an interface for repository and then make an instance of the repository into service Class via the Constructor now both the high level and low level modules depend on an abstraction.

SOLID is just a set of guidelines, not strict rules.
