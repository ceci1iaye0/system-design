# System Design

## SOLID Principles

- Object-oriented design principles

#### Single Resposibility

- A class / function should only have **a single reason to change**
- A class / function should only **do one thing**

#### Open / Closed

- A class / function should be **open to extension**, but closed for modifications
- Promotes re-usability
- E.g., A child class can extend functions of the parent class

#### Liskov Substitution

- An object of **a superclass should be replaceable with an object of its subclasses without altering the correctness** of that object
- E.g., Rectangle superclass has setHeight() and setWidth(). Square extends Rectangle, then call setHeight(4) and setWidth(5). The height and width should be equal for a Square. Thus, a Square extending a Rectangle class breaks the Liskov substitution principle.

#### Interface Segregation

- No code should be forced to **depend on functions it does not use**
- E.g., User interface class has getSalary(). Student class that implements the User has to implement getSalary() despite it does not need that method.

#### Dependency Inversion

- High-level modules should not depend on low-level modules, but both should depend on **abstractions instead of concretions**
- App / functions should be **loosely coupled**
- E.g., The logic for making HTTP requests should be abstracted out from the .jsx file.
