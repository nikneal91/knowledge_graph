material:: course
main:: #quarkus

- ## Need for Quarkus
	- Java and J2EE application becomes huge and when the containers and k8s comes into the picture the startup time of java application caused developers to shy away from java and use node.js or any other faster framework
	- To address these issue microprofile and small java footprints gave birth to quarkus which has all the eco-system of java , but still fast , modular and smaller in size to fit the needs of cloud and microservices
- ## Quarkus Benefits
  collapsed:: true
	- Build Time vs Runtime benefit - offload a lot of things at build time ,hence faster runtime execution and native compilation ability
	- Unification of imperative and [[reactive programming]] - no need to decide upfront , both reactive programming and imperative programming can co-exists in the same application.
	- Enhancing Developer Joy
		- Zero-config live coding
		- Auto-provision services
		- Continuous Testing
		- Dev UI
		- Cli
	-
- ## Quarkus Internals
  collapsed:: true
	- Dont be dynamic
	  collapsed:: true
		- Quarkus statically checks all the class it needs , rather than at runtime the jvm decides to load and unload classes which is time consuming , one such example is database libraries where java unnecessarily load/unload all other libraries before finalizing to it. so if we are using postgresql library , quarkus just load the classes related to it.
	- Dead Code Elimination / inlining
	- Extensible build process so libraries can participate
	- Jandex indexing ( offline reflection)
	- Don't make humans tell the computer what it knows
	- Continuous profiling and shaving
	- Be reactive without forcing humans to do reactive
		-
- ## Quarkus - create an application