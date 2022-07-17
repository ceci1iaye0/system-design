# System Design

## SOLID Principles

- Object-oriented design principles

### Single Resposibility

- A class / function should only have **a single reason to change**
- A class / function should only **do one thing**

### Open / Closed

- A class / function should be **open to extension**, but closed for modifications
- Promotes re-usability
- E.g., A child class can extend functions of the parent class

### Liskov Substitution

- An object of **a superclass should be replaceable with an object of its subclasses without altering the correctness** of that object
- E.g., Rectangle superclass has setHeight() and setWidth(). Square extends Rectangle, then call setHeight(4) and setWidth(5). The height and width should be equal for a Square. Thus, a Square extending a Rectangle class breaks the Liskov substitution principle.

#### Interface Segregation

- No code should be forced to **depend on functions it does not use**
- E.g., User interface class has getSalary(). Student class that implements the User has to implement getSalary() despite it does not need that method.

### Dependency Inversion

- High-level modules should not depend on low-level modules, but both should depend on **abstractions instead of concretions**
- App / functions should be **loosely coupled**
- E.g., The logic for making HTTP requests should be abstracted out from the .jsx file.

## Client Side Rendering, Server Side Rendering, or Pre-Rendering

### What is it?

| Client Side Rendering                                                       | Server Side Rendering                                                        | Pre-Rendering                                                                                                                             |
| --------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| Compile HTML pages with static data on server &rarr; `fetch` data on client | `fetch` data on server &rarr; compile HTML pages with fetched data on server | - Compile HTML pages once at build time &rarr; store the cached HTML in a CDN &rarr; return the static cached page <br> - Hybrid approach |
| - React.js <br> - Angular.js                                                | - Java <br> - React on Express.js                                            | - Next.js                                                                                                                                 |

### Pros and Cons

|          | Client Side Rendering                                                 | Server Side Rendering                                                                                                                                                                | Pre-Rendering                                                            |
| -------- | --------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------ |
| **Pros** | - Fast rendering after initial loading                                | - Good Search Engine Optimisation (SEO) <br> - Fast initial loading                                                                                                                  | - Better SEO <br> - Lesser requests than SSR                             |
| **Cons** | - Low SEO as it crawls on the static data <br> - Slow initial loading | - Lots of server requests <br> - Full page reloads <br> - More expensive as it takes up more CPU to compile the HTML pages <br> - Slow rendering when app has a lot of interactivity | - Need to provide user-friendly UI for first loading if data is required |

### Usage

| Client Side Rendering                                                                                        | Server Side Rendering                                                                     | Pre-Rendering                                                                |
| ------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| - App has dynamic data and interactive UI <br> - Does not require SEO e.g., internal apps <br> - Large users | - App has minimal interactivity / more static pages <br> - Require SEO <br> - Small users | - If you don’t want to use SSR, but you need to improve loading time and SEO |
