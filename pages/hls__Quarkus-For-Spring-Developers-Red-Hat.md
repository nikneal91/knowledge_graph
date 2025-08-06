file:: [Quarkus-For-Spring-Developers-Red-Hat.pdf](assets/Quarkus-For-Spring-Developers-Red-Hat.pdf)
source-code::  [Github Link](https://github.com/quarkus-for-spring-developers/examples)
file-path:: assets/Quarkus-For-Spring-Developers-Red-Hat.pdf

- Quarkus is used in microservices architectures, event-driven architectures, serverless, functions-as-a-service, edge computing, and IoT
  hl-page:: 8
  ls-type:: annotation
  id:: 689088f3-52ac-4ee2-9cbf-0d741eb5f87e
  hl-color:: yellow
	-
- Challenge #1: Composition of Distributed Applications
  ls-type:: annotation
  hl-page:: 10
  hl-color:: red
  id:: 689089d5-5ac6-4c15-b4f9-882d4d69d300
	- A set of design principles, known as Reactive Systems or Reactive Principles, attempt to address some of these challenges
	  ls-type:: annotation
	  hl-page:: 10
	  hl-color:: red
	  id:: 68908a9e-b8e5-499d-8f25-25c2b9a9d01a
-
- ### Reactive systems
  ls-type:: annotation
  hl-page:: 10
  hl-color:: yellow
  id:: 68908afd-4761-433a-a323-4c9af24b5f67
- Reactive Systems are flexible, loosely-coupled, scalable, and highly responsive, making them more maintainable and extensible. Reactive Systems are also resilient when faced with failure.
  ls-type:: annotation
  hl-page:: 10
  hl-color:: yellow
  id:: 68908b13-2f23-4d38-b3c4-e8e9d97e84e2
	- Responsive - The system
- MicroProfile capabilities [1.13] include application-level metrics, health checks, distributed tracing, standardized external configuration, fault tolerance, JSON Web Token (JWT) propagation, OpenAPI integration, and CDI
  ls-type:: annotation
  hl-page:: 15
  hl-color:: yellow
  id:: 68908dd0-cc5c-4f79-951a-2a82eca77790
- Like Spring, Quarkus reads configuration properties from several sources, in decreasing
  hl-page:: 20
  ls-type:: annotation
  id:: 68908f76-badc-41b3-9dd2-5bea26b44bdc
  hl-color:: green
  priority:
	- 1. System properties.
	  2. Environment variables.
	  3. A file named .env placed in the current working directory (the directory fromwhich the application was started).
	  4. application.properties (or a file named application.yml or application.
	  yaml, if using the Quarkus YAML extension) placed in the /config directory.
	  5. application.properties (or a file named application.yml or application.
	  yaml, if using the Quarkus YAML extension) placed in the src/main/resources
	  directory.
-
- Java was created when the cloud, containers, and container orchestration systems such as Kubernetes [1.1] did not exist. The historical Java stack consisted of applications deployed into Java application servers. In that architecture, each application server hosted multiple applications and provided additional services, such as transaction management, caching, connection pooling, and more. These application servers focused on providing the Java2 Enterprise Edition (J2EE)
  ls-type:: annotation
  hl-page:: 8
  hl-color:: green
  id:: 68919f69-dc3a-456a-b7ed-ae5e518bbf33
- ported and simplified capabilities such as access to a database, asynchronous messaging, authentication and authorization of users, and web services. Many architects and developers have promoted Spring as arguably one of the most popular frameworks to build applications. Emergence of Microservices Over time, large, monolithic applications became harder to scale. Many teams needed to work in parallel on the same project in the same source code repository. Any change to one part of an application affected other developers working on other parts of the application, while also forcing testing and redeployment of the entire application. A single application deployment may have consisted of tens of servers and required hours of offline maintenance. The entire application needed additional instances deployed to handle increased loads that might affect only a subset of its capabilities. Development teams were also becoming more agile, wanting to deliver business capabilities faster. Gone were the days of waterfall design, where an entire system needed to be designed before a line of code was written. Agile development helps enable teams to deliver smaller subsets of business capabilities faster. It also allows for smaller development teams, where each team can focus on a small subset of the capabilities an overall system provides. These technical and nontechnical issues partly influenced the rise of microservices architectures. A microservices architecture brings together many small applications to form a larger system, communicating using HTTP, TLS, or asynchronous messaging. A microservices architecture allows for the decoupling of functionality around specific business capabilities, where each capability can be owned, maintained, tested, and deployed independently. Additionally, microservices can more efficiently consume the available CPU and memory, which is not always possible in a monolithic application. A single business capability can scale independently of other capabilities. Spring Boot The shift towards microservices also led to the introduction of Spring Boot in 2014. One of the most powerful features of Spring Boot was its ability to package all the needed libraries within a single JAR file. This feature allowed quick bootstrapping of an application without deploying it into a separate Servlet container. Instead, Spring Boot embeds a web container (i.e., Apache Tomcat, Eclipse Jetty, or Undertow) inside the
  ls-type:: annotation
  hl-page:: 9
  hl-color:: green
  id:: 68919fb9-6e96-4aa3-96ed-d345bf0ec9c6
- [:span]
  ls-type:: annotation
  hl-page:: 9
  hl-color:: green
  id:: 68919fc6-3948-46f5-9e2f-daa52bdf2d30
  hl-type:: area
  hl-stamp:: 1754374086088
- [:span]
  ls-type:: annotation
  hl-page:: 9
  hl-color:: blue
  id:: 68919fef-8e05-4590-b326-0b8110630650
  hl-type:: area
  hl-stamp:: 1754374124614