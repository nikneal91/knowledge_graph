alias:: reactive
tags:: #quarkus #mutiny 
source:: [jbang](file:///C:/Users/nikhilsharma03/Code/jbang)

- ## ✅  **1. Why Mutiny Exists**
  collapsed:: true
	- Reactive programming in Java was dominated by **RxJava** and **Reactor**, but they had:
		- Steep learning curves.
		- Hard-to-read APIs (lots of `map`, `flatMap`, `subscribe`).
		- Debugging nightmares.
	- Mutiny focuses on:
		- **Fluent, readable APIs** (verbs instead of operators).
		- **Event-driven design** (think: “what happens when…”).
		- **Built for Quarkus** (integrates with Vert.x, RESTEasy Reactive, Hibernate Reactive, etc.).
- ## ✅  **2. Core Concepts**
  collapsed:: true
	- Mutiny has two main building blocks:
		- #### **Uni**  → Represents  **one item**  (or a failure)
		  Example: A database fetch that returns a single user.
		- #### **Multi**  → Represents  **a stream of items**  (0..N items)
		  Example: Reading lines from a file or receiving Kafka messages.
- ## ✅  **3. Mutiny Design Philosophy**
  collapsed:: true
	- **Be explicit about what happens on success and failure.**
	- **Readable, fluent APIs:** Instead of `flatMap`, Mutiny uses verbs like:
		- `onItem().transform(...)`
		- `onFailure().recoverWithItem(...)`
		  
		  This makes code **self-explanatory**
- ## ✅  **4. Getting Started with Uni**
  collapsed:: true
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
- ## ✅ **5. Using Multi**
  collapsed:: true
	- ```java
	  import io.smallrye.mutiny.Multi;
	  
	  public class MutinyMultiExample {
	      public static void main(String[] args) {
	          Multi.createFrom().items(1, 2, 3, 4, 5)
	              .onItem().transform(n -> n * 2)
	              .subscribe().with(
	                  item -> System.out.println("Got: " + item),
	                  failure -> System.err.println("Failed: " + failure),
	                  () -> System.out.println("Done")
	              );
	      }
	  }
	  
	  ```
	- > **What happens here?** 
	  A Multi emits `1, 2, 3, 4, 5`.
	  Each item is transformed by `n * 2`.
	  subscribe().with()` handles items, failure, and completion.
- ## ✅  **8. Why Uni and Multi instead of [[CompletableFuture]] or [[Stream]] ?**
  collapsed:: true
	- ** [[CompletableFuture]] ** handles only **one result** (like Uni), but ==no built-in failure recovery== chain.
	- **Java [[Stream]] ** is synchronous and pull-based.
	- **Uni/Multi** are push-based, non-blocking, composable, and built for **reactive streams spec**.
- ## ✅  **9. Integrating with [[Quarkus]] **
  collapsed:: true
	- Mutiny is deeply integrated in [[Quarkus]] :
	- **RESTEasy Reactive:** Return `Uni<Response>` or `Multi<Item>` in endpoints.
	- ** [[Hibernate Reactive]] :** Fetch entities using `Uni`.
	- **Messaging ([[Kafka]], AMQP):** `Multi` for streams of messages.
-
-
-
-
-