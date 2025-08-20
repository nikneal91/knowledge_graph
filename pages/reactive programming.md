alias:: reactive
tags:: #quarkus

- ## ✅  **1. Why Mutiny Exists**
	- Reactive programming in Java was dominated by **RxJava** and **Reactor**, but they had:
	- Steep learning curves.
	- Hard-to-read APIs (lots of `map`, `flatMap`, `subscribe`).
	- Debugging nightmares.
- Mutiny focuses on:
	- **Fluent, readable APIs** (verbs instead of operators).
	- **Event-driven design** (think: “what happens when…”).
	- **Built for Quarkus** (integrates with Vert.x, RESTEasy Reactive, Hibernate Reactive, etc.).
- ## ✅  **2. Core Concepts**
  
  Mutiny has two main building blocks:
	- #### **Uni**  → Represents  **one item**  (or a failure)
	  
	  Example: A database fetch that returns a single user.
	- #### **Multi**  → Represents  **a stream of items**  (0..N items)
	  
	  Example: Reading lines from a file or receiving Kafka messages.
- ## ✅  **3. Mutiny Design Philosophy**
- **Be explicit about what happens on success and failure.**
- **Readable, fluent APIs:** Instead of `flatMap`, Mutiny uses verbs like:
	- `onItem().transform(...)`
	- `onFailure().recoverWithItem(...)`
	  
	  This makes code **self-explanatory**
- ## ✅  **4. Getting Started with Uni**
	- ```java
	  import io.smallrye.mutiny.Uni;
	  
	  public class MutinyExample {
	      public static void main(String[] args) {
	          Uni.createFrom().item("Hello Mutiny")
	              .onItem().transform(item -> item + "!")
	              .subscribe().with(
	                  item -> System.out.println("Received: " + item),
	                  failure -> System.err.println("Failed: " + failure)
	              );
	      }
	  }
	  
	  ```
	- **What happens here?**
	- `Uni.createFrom().item("Hello Mutiny")` → Creates a Uni with one value.
	- `onItem().transform(...)` → Transforms the result.
	- `subscribe().with(...)` → Consumes the Uni with **success** and **failure** handlers.