link:: [Github](https://github.com/iluwatar/java-design-patterns)
website:: https://java-design-patterns.com/

- ## Creational Design Patterns
  collapsed:: true
  > Focus: Object creation mechanisms, making system independent of how objects are created.
	- Singleton – Ensure only one instance exists globally.
	- Factory Method – Create objects without exposing creation logic.
	- Abstract Factory – Provide an interface to create families of related objects.
	- Builder – Construct complex objects step-by-step.
	- Prototype – Create objects by cloning existing ones.
- ## Structural Design Patterns
  collapsed:: true
  > Focus: Composition of classes and objects to form larger structures.
	- Adapter – Convert one interface into another expected by clients.
	- Bridge – Separate abstraction from implementation.
	- Composite – Treat individual objects and compositions uniformly.
	- Decorator – Add behavior dynamically to objects.
	- Facade – Provide a unified interface to a set of interfaces.
	- Flyweight – Minimize memory usage by sharing objects.
	- Proxy – Control access to an object (remote, virtual, or protective).
- ## Behavioral Design Patterns
  collapsed:: true
  > Focus: Communication between objects.
	- Chain of Responsibility – Pass request along a chain of handlers.
	- Command – Encapsulate a request as an object.
	- Interpreter – Define grammar and interpreter for a language.
	- Iterator – Provide a way to sequentially access elements.
	- Mediator – Define an object that controls communication between objects.
	- Memento – Capture and restore object’s state.
	- Observer – Define a one-to-many dependency (pub-sub).
	- State – Allow object to alter behavior when state changes.
	- Strategy – Define a family of algorithms, encapsulate them.
	- Template Method – Define skeleton of an algorithm in a method.
	- Visitor – Represent an operation to be performed on elements of an object structure.
- ## Concurrency Patterns (Java Specific)
  collapsed:: true
  > Focus: Handling multithreading and parallelism.
	- Thread Pool (Executor Service) – Reuse fixed number of threads.
	- Future & Callable – Handle async computations.
	- Producer-Consumer – Separate work submission and processing.
	- Read-Write Lock – Improve concurrent read access.
	- Double-Checked Locking – Efficient thread-safe Singleton.
- ## Enterprise Patterns (Java EE / Spring)
  collapsed:: true
	- DAO (Data Access Object) – Abstract persistence layer.
	- Service Locator – Find services dynamically.
	- Business Delegate – Reduce coupling between presentation and business layers.
	- Transfer Object (DTO) – Transfer data between layers.
	- MVC (Model-View-Controller) – Separate presentation, business logic, and model.