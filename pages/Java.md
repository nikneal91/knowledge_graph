website:: https://dev.java/learn/
reference:: #Index

- A programming language. Current version in use is Java 21
- A 30 year old programming language , J2EE is 25 years old now.
- [[jbang]]
- [[Java Module System]] - tutorial of java 9
- [[Quarkus]]
- [[Kubernetes]]
- [[Docker]]
- [[Podman]]
-
- ---
- ## Java for small Coding Task
	- Slides : https://horstmann.com/presentations/2025/javaone/#(1)
	- Course : {{video https://www.youtube.com/watch?v=04wFgshWMdA}}
		- ```java
		  ///usr/bin/env java --source 25 "$0" "$@" ; exit $?
		  import java.util.List;;
		  public class MyClass {
		          public static void main(String[] args) {
		                  var mylist = List.of("one", "two", "three", "four", "five");
		                  System.out.println("Hello scripting in java ");
		                  System.out.println(mylist);
		          }
		  }
		  ```
			- Use the above line on the top of java program to make it work as a script in linux.