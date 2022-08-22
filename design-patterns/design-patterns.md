# Design Patterns

## Creational Patterns

### Singleton

- Ensure that a class / object has a **single instance**, and it uses a global variable to store that instance
- When to use?
  - To maintain a global state where the rest of the code needs to access and operate on a common resource
  - To cache information

```javascript
class DBClient {
    async getConnection(){...}
}

export default new DBClient();
```

## Behavioral Patterns

### Observer

- Similar to a subscription mechanism where subjects will notify observers on any changes
- MVC is the first implementation of the observer pattern
  - Model = subject, which holds the data and states
  - View = observer, which are the different components that get the data from the subject
- E.g., For updating, filtering

```javascript
class CategoryDropdown {
  constructor() {
    this.categories = ["food", "beverages", "electronics"];
    this.subscriber = [];
  }

  subscriber(observer) {
    this.subscriber.push(observer);
  }

  onChange(selectedCategory) {
    this.subscriber.forEach((observer) => observer.update(selectedCategory)); // Send values to subscribes to update the individual dropdown
  }
}

class FilterDropdown {
  constructor(filterType) {
    this.filterType = filterType;
    this.items = [];
  }

  update(category) {...}
}

const categoryDropdown = new CategoryDropdown();

const brandDropdown = new FilterDropdown("brand");
const priceDropdown = new FilterDropdown("price");

categoryDropdown.subscribe(brandDropdown); // Subscribe to the category dropdown observer
categoryDropdown.subscribe(priceDropdown);
```

### Strategy

- A group of algorithms, in which a specific algorithm will be selected for use during runtime
- Advanced if-else statement
- Pros:
  - Code reusability
  - Achieves Open-closed SOLID principle where new strategies can be added without having to change existing code
- E.g., Payment strategies

```typescript
type TCustomerInfo = {
  name: string;
  email: string;
  accountNumber?: string;
  cardNumber?: string;
};

class PaymentMethodStrategy {
  BankAccount(customerInfo: TCustomerInfo) {
    const { name, accountNumber } = customerInfo;
    // implementation
  }

  CreditCard(customerInfo: TCustomerInfo) {
    const { name, cardNumber } = customerInfo;
    // implementation
  }

  PayPal(customerInfo: TCustomerInfo) {
    const { name, emailAddress } = customerInfo;
    // implementation
  }
}

class Checkout {
  constructor(strategy = "CreditCard") {
    this.strategy = PaymentMethodStrategy[strategy];
  }
  changeStrategy(newStrategy) {
    this.strategy = PaymentMethodStrategy[newStrategy];
  }
}
```

## Structural Patterns

### Decorator

- **Wrapping one piece of code with another** or **apply a wrapper around a function**
- When to use?
  - To enhance the functionality of the function without modifying the underlying function
- Pros:
  - Provides a clearer syntax

```javascript
const addDescription = () => {
  target.description = "test";
};

@addDescription // Decorator
class Product {}

console.log(Product.description); // test
```
