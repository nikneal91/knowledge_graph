main:: java
topic:: Java Module System 
version:: java9 onwards

- ## `Introduction`
  collapsed:: true
	- >Venkat Subramaniam dives straight into Java Modules—why they matter and how to migrate, grounded in real-world experience migrating projects from Java 8 to Java 11/12. Here's the raw breakdown:
- ## **Java Modules Benefits**
	- **Modularize the JDK itself**
	  collapsed:: true
		- Java 8’s `rt.jar` was a massive ~68 MB monolith. Java 9+ broke that into 70–98 clearly separated modules you can include or exclude as needed.
	- **Enforce real boundaries**
	  collapsed:: true
		- Modules allow true encapsulation—unlike before when “don’t use this” was just advice, now unauthorized access is blocked.
	- **Boost security**
	  collapsed:: true
		- You can’t spoof packages across JARs silently anymore—modules prevent that kind of vulnerability.
	- **Fail fast**
	  collapsed:: true
		- Missing dependencies cause startup failures, not “class not found” nightmares at 2 AM.
	- ```
	  java --list-modules
	  ```
- ## **What Is a Module?**
  collapsed:: true
	- A module comprises you classes (interfaces, enums, etc.) plus:
	  collapsed:: true
		- `requires` declarations (what it depends on)
		- `exports` declarations (what it exposes)
	- A clean modular handshake—you don’t export what you don’t mean to, and you can’t use what you haven’t explicitly required.
- ## **Three Module Types**
  collapsed:: true
	- **Unnamed Modules** – All legacy code on the classpath—no descriptor, zero restrictions.
	- **Automatic Modules** – Existing JARs dropped onto the module path; picked up automatically with a generated module name.
	- **Explicit Named Modules** – JARs with `module-info.java`; fully controlled names, dependencies, and exports.
- ## **Interaction Rules**
  collapsed:: true
	- | Module | Restriction|
	  |Unnamed ↔ Unnamed:| unrestricted.|
	  |Automatic → Unnamed:| allowed.|
	  |Unnamed → Automatic:| blocked.|
	  |Explicit ↔ Explicit: |allowed.|
	  |Explicit → Automatic: |allowed.|
	  |Automatic → Explicit:| blocked (explicit modules only expose what they export).|
- ## **Migration Strategy**
  collapsed:: true
	- 1. **Always** start with working legacy code on the classpath.
	- 2. Verify it still runs under newer Java versions.
	- 3. Move to module path next—but beware of `split package` issues (same package in multiple JARs won’t pass the module path check).
	- 4. Give automatic modules sensible names via `Automatic-Module-Name` in the manifest.
	- 5. Start migrating from top of the dependency tree downward—not the other way—because classpath cannot talk to module path and will break.
	- 6. Declare `requires` and `exports` explicitly to satisfy the module handshake.
	  
	  ---
	- ### TL;DR
	  
	  > Modularizing your Java app means moving from a tangled classpath to a well-defined module architecture—one that improves maintainability, security, and startup reliability. Venkat illustrates how migrating in small, dependency-aware steps preserves functionality while unlocking those benefits.
	  
	  > Want help crafting specific `module-info.java` files or navigating Maven/Gradle setups next? I’ve got your back—let's do this.