# SOLID Principles

- Object-oriented design principles
- To ensure that code is easy to understand, manage, maintain, and **extensible**
- To **reduce code dependencies** so that adding or changing a part of the code does not break the app

## Single Responsibility

- A class / function should only have **a single reason to change**
- A class / function should only **do one thing**

## Open-Closed

- A class / function should be **open to extension**, but closed for modifications
- Promotes re-usability
- E.g., A function with a bunch of if or switch statements violates the open-closed principle
- E.g., A child class can extend functions of the parent class

## Liskov Substitution

- An object of **a superclass should be replaceable with an object of its subclasses without altering the correctness** of that object
- E.g., All squares are rectangle but vice versa is not true, and the Liskov's principle fails. Rectangle superclass has setHeight() and setWidth(). Square extends Rectangle, then call setHeight(4) and setWidth(5). The height and width should be equal for a Square. Thus, a Square extending a Rectangle class breaks the Liskov substitution principle.

## Interface Segregation

- No code should be forced to **depend on functions it does not use**
- E.g., User interface class has getSalary(). Student class that implements the User has to implement getSalary() despite it does not need that method.

## Dependency Inversion

- Low-level modules should not rely on high-level modules. **Abstractions should be used instead implementations**.
- E.g., If the payment service needs to be changed to include SamsungPay, the code should be scalable for extension.

```javascript
type PaymentTransaction = "Success" | "Failure" | "Bounded";

interface IPaymentTransactionResult {
  result: PaymentTransaction;
  message?: string;
}

interface IPaymentService {
  pay(to: string, amount: number): Promise<IPaymentTransactionResult>;
}

class GooglePayService implements IPaymentService {
  pay(to: string, amount: number): Promise<IPaymentTransactionResult> {
    // implementation
  }
}

class SamsungPayService implements IPaymentService {
  pay(to: string, amount: number): Promise<IPaymentTransactionResult> {
    // implementation
  }
}
```
