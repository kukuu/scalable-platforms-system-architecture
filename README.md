## System Design Architecture for scalable robust digital platforms

Software architecture refers to the high level structures of a software system and the discipline of creating such structures and systems. Each structure comprises software elements, relations among them, and properties of both elements and relations.

The architecture is a blend of technical decisions and architectural patterns, and considered the root of a software project to ensure its scalability, resilience, robustness, security, quality, cost effectiveness and longevity.

The architecture is made so the code structure can satisfy business goals and every software prerequisite that is being developed while exemplifying transversal attributes such as performance, security, quality, scalability, maintainability, manageability, elasticity and usability.

You can use multiple patterns in a single system to optimize each section of code with the best architecture.

### Architectural Patterns 

There are many recognized architectural patterns and styles, among them:


1. Client-server : 2-tier, 3-tier, n-tier, Cloud computing exhibits this style: Leveraging cloud technology services, particularly AWS, Azure, or Google Cloud, architecting the platform for scalability and reliability. Cloud-native solutions will allow for easy scaling and disaster recovery planning.

2. Layered (or multilayered architecture eg. MVC)

3. Microservices architecture

4. Event Driven  / Implicit invocation 

5. Monolithic application : A monolithic application describes a single-tiered software application in which
 the user interface and data access code are combined into a single program from a single platform.

6. Micro-kernael (COTS/Plugin)

7. Publish/Subscribe

8. Component-based

9. Data-centric



By combining the technologies, methodologies and practices below, you can successfully build a digital platform that will be highly scalable, reliable, maintainable and cost effective. The platform could efficiently handle growing user loads, recover from failures, and provide actionable insights through comprehensive monitoring and observability. This approach will ensure the platform's resilience and responsiveness, meets the demands of a dynamic digital landscape.

__Methodologies & _Practices_:

- System Design Architecture: Start by carefully designing the architecture of the digital platform. follow established software engineering standard methodologies such as the SOLID principles, Domain-Driven Design (DDD) to ensure a maintainable and scalable system and also Security and Project Management methodolgies and guidelines like OWASP, TOGAF, Agile etc.

  
![image](https://github.com/kukuu/scalable-platforms-system-architecture/assets/10147828/ca5a8d17-1210-47ea-90f8-db5e310e9ea5)


- Node.js and TypeScript: Node.js was chosen as the backend runtime due to its efficiency and non-blocking I/O. TypeScript was employed to bring strong typing and improved maintainability to the codebase.

-  Divide the platform into microservices (where necessary), each responsible for a specific domain or functionality. Event-driven architecture using message queues like RabbitMQ or Kafka facilitated asynchronous communication between these microservices.

- Integration and DevOps: Common integration tasks were streamlined by implementing CI/CD pipelines. Tools like Jenkins or GitLab CI can be used to automate testing and deployments. Infrastructure as Code (IaC) with tools like Terraform or AWS CloudFormation was employed for infrastructure provisioning.

           https://github.com/kukuu/integration

- Kubernetes: Containerization using Docker and orchestration with Kubernetes enabled easy management and scaling of microservices. Kubernetes provided features like load balancing, self-healing, and rolling updates.

- Monitoring and Observability: Monitoring and observability solutions are implemented using Prometheus, Grafana and Pager. This allowed for real-time monitoring of application health, resource utilization, and the ability to set up alerts for proactive issue resolution.


## Principles of Software Design Architecture

![image](https://github.com/kukuu/integration/assets/10147828/c3c69b95-1a81-4703-931a-5ddef8e19aa4)


```

i. Identify Business goals 
       
ii. Quality Attributes 
       
iii. Architecture

iv. Design

v. Code (Implementation)

```

## Software Architecture Design Decision

![image](https://github.com/kukuu/integration/assets/10147828/24149165-3a03-4194-afd9-292f20fc3e1a)



## Software Architecture Design Patterns

### Client Server Multi-tier


![image](https://github.com/kukuu/integration/assets/10147828/8921e2ac-676b-4508-be2a-f4c3d64f2c20)


### Layered (n-tier) architecture

This approach is probably the most common because it is usually built around the database, and many applications in business naturally lend themselves to storing information in tables.
 
#### MVC
 
 The code is arranged so the data enters the top layer and works its way down each layer until it 
 reaches the bottom, which is usually a database. Along the way, each layer has a specific task, 
 like checking the data for consistency or reformatting the values to keep them consistent. 
 It’s common for different programmers to work independently on different layers
 
 Just above the database is the model layer, which often contains business logic and information 
 about the types of data in the database. At the top is the view layer, which is often CSS, JavaScript, 
 and HTML with dynamic embedded code. In the middle, you have the controller, which has various rules
 and methods for transforming the data moving between the view and the model.
 
 The Model-View-Controller (MVC) structure, which is the standard software development approach offered by most of the popular web frameworks, is clearly a layered architecture. 

 This architecture can also contain additional open layers, like a service layer, that can be used to access shared services only in the business layer but also get bypassed for speed.


#### Benefits

The advantage of a layered architecture is the separation of concerns, which means that each layer can focus solely on its role. This makes it:

i.  Maintainable

ii.  Testable

iii. Easy to assign separate "roles"

iv.  Easy to update and enhance layers separately



#### Caveats

i.  Source code can turn into a “big ball of mud” if it is unorganized and the modules don’t have clear roles or relationships.

ii. Code can end up slow thanks to what some developers call the “sinkhole anti-pattern.” Much of the code can be devoted to   passing data through layers without using any logic.

iii. Layer isolation, which is an important goal for the architecture, can also make it hard to understand the architecture without understanding every module.

iv. Coders can skip past layers to create tight coupling and produce a logical mess full of complex interdependencies.
Monolithic deployment is often unavoidable, which means small changes can require a complete redeployment of the application.

#### Best for

i.   New applications that need to be built quickly

ii   Enterprise or business applications that need to mirror traditional IT departments and processes

iii. Teams with inexperienced developers who don’t understand other architectures yet

iv.  Applications requiring strict maintainability and testability standards
 
### Microservice

A Microservices architecture refers to an application which is constructed from a number of independent services called Microservices.  Each microservice is a 
self-contained module that performs a discrete group of functions and provides unique business capabilities. The individual services boosts of its own data federation unlike monoliths for  deployment. The term micro does not mean that the modules that make up the system are necessarily small, just independent. In fact, they each may have a website, web service, windows service and a database. 

Communication between each of these modules is achieved via web service calls and messages on a service bus that calls to and collects the relevant data/information from each module. 
 
Choosing which architecture is right for your project is a very complex task. Complexity, flexibility, size, time frames, diversity of the team, cost-effectivenes/budget and specific conditions of the project are just some of the factors that need to be considered when deciding which software architecture is the best for your project.

With Monoliths, minor changes to particular parts of the application, may require a re-deployment of the whole application. Delta changes cannot be detected. Not very good for scaling and performance.

#### The Architectural Pattern

Microservices architecture is a distributed system of single self-contained units and an approach to application development in which a large application is built as a suite of modular services. Each module supports a specific business goal and uses a simple, well-defined interface to communicate with other sets of services.

By splitting your app into small units every part of it is independently deployable and scalable, can be written by different teams and in different programming languages and can be tested individually.

The micro-service  applications is capable of running in their own memory space, data federation and scale independently from each other across potentially many separate machines. 

When you choose to build your application as a set of microservices, you need to decide how your application’s clients will interact with the microservices. With a monolithic application there is just one set of (typically replicated, load‑balanced) endpoints. In a microservices architecture, however, each microservice exposes a set of what are typically fine‑grained endpoints.

Services must handle requests from the application’s clients. Furthermore, services must sometimes collaborate to handle those requests. They must use an inter-process communication protocol for translations and forwarding requests. Use asynchronous non-blocking messaging for inter-service communication. Services communicating by exchanging messages over messaging channels. Examples of asynchronous messaging technologies are Apache Kafka (Event Driven) and RabbitMQ (Messaging). Communication can also be established using REST.

#### Benefits and Motivation

- Loose coupling since it decouples clients from services
- Small individual components
- Easy to maintain
- Offers parallel development
- Independent deployment
- Rapid iteration
- Feature additions - enrichments
- Confidence with CI/CD
- Improved availability since the message broker buffers messages until the consumer is able to process them. Result in asynchronous  data handling during request, response
- Supports a variety of communication patterns including request/reply, notifications, request/async response, publish/subscribe, publish/async response etc
- Agile compliant: The modular approach of Microservices architecture works well with an agile management style 
as it supports the slicing and splitting up of smaller work increments and tasks which goes hand-in-hand 
with projects using an agile methodology.
- Reduced system downtime: Microservices provide the flexibility to change parts of the solution 
without affecting the solution as a whole which is key in providing a reliable solution without


#### Caveats

i.  The services must be largely independent or else interaction can cause the cloud to become imbalanced.

ii. Not all applications have tasks that can’t be easily split into independent units.

iii. Performance can suffer when tasks are spread out between different microservices. The communication costs can be significant.

iv. Too many microservices can confuse users as parts of the web page appear much later than others. Anti-AJAX


#### Best for

i.   Websites with small components

ii.  Corporate data centers with well-defined boundaries

iii. Rapidly developing new businesses and web applications

iv.   Development teams that are spread out, often across the globe


####  How to convert monolithic to Microservices

```

1. Look for probable targets by researching the Monolith and warm up with a simple and fairly decoupled capability. 
   i.e Authentication and then Profile

2. Minimize Dependency Back to the Monolith. i.e Buying and promotion. 
   Buying has dependencies including promotion. Decouple promotions from buying.

3. Split Sticky Capabilities Early.

4. Decouple Vertically and Release the Data Early.

5. Decouple What is Important to the Business and Changes Frequently.

6. Decouple Capability and not Code.

7. Go Macro First, then Micro.

```

#### NodeJS Microservice

- https://github.com/kukuu/microservices

- https://github.com/kukuu/microservices/tree/master/microservice-nodejs-express



#### microservice transaction
![image](https://github.com/kukuu/integration/assets/10147828/cd910655-6da1-4a00-ba00-16efabc7b0a2)


#### SPRING BOOT JAVA Microservice

![image](https://github.com/kukuu/integration/assets/10147828/e48fa1d1-8fe2-4c30-8e8d-43274d263898)

### Space-based architecture (Cloud)

The space-based architecture is designed to avoid functional collapse under high load by splitting up both the processing and the storage between multiple servers. 

The data is spread out across the nodes just like the responsibility for servicing calls. The name “space-based” refers to the “tuple space” of the users, which is cut up to partition the work between the nodes. 

The space-based architecture supports things that have unpredictable spikes by eliminating the database.

Examples are PaaS, SaaS, IaaS etc.

####  Caveats

i.  Finding an average or doing a statistical analysis—must be split up into subjobs, spread out across all of the nodes, and then aggregated when it’s done.

ii.  Transactional support is more difficult with RAM databases.

iii. Generating enough load to test the system can be challenging, but the individual nodes can be tested independently.

iv. Developing the expertise to cache the data for speed without corrupting multiple copies is difficult.

#### Best for

i.  High-volume data like click streams and user logs

ii. Low-value data that can be lost occasionally without big consequences—in other words, not bank transactions
Social networks.

### Event-driven / Composition architecture

Many programs spend most of their time waiting for something to happen. Sometimes there’s data that needs processing, and other times there isn’t. Common within network operations, and human driven.

The event-driven architecture helps manage this by building a central unit that accepts all data and then delegates it to the separate modules that handle the particular type. This handoff is said to generate an “event,” and it is delegated to the code assigned to that type. Functional programming. 

Programming a web page with JavaScript involves writing the small modules that react to events like mouse clicks or keystrokes. The browser itself orchestrates all of the input and makes sure that only the right code sees the right events. Many different types of events are common in the browser, but the modules interact only with the events that concern them. This is very different from the layered architecture where all data will typically pass through all layers. 

#### Benefits

i.   Are easily adaptable to complex, often chaotic environments

ii.  Scale easily

iii. Are easily extendable when new event types appear


#### Caveats

i.  Testing can be complex if the modules can affect each other. While individual modules can be tested independently, the interactions between them can only be tested in a fully functioning system.

ii.  Error handling can be difficult to structure, especially when several modules must handle the same events.
When modules fail, the central unit must have a backup plan.

iii. Messaging overhead can slow down processing speed, especially when the central unit must buffer messages that arrive in bursts.

iv.  Developing a systemwide data structure for events can be complex when the events have very different needs.

v. Maintaining a transaction-based mechanism for consistency is difficult because the modules are so decoupled and independent.

#### Best for:

i.  Asynchronous systems with asynchronous data flow

ii.  Applications where the individual data blocks interact with only a few of the many modules

iii. User interfaces

### Microkernel (Plug-in) architecture - AKA COTS

The microkernel architecture pattern (aka plug-in architecture pattern) is a natural pattern for implementing product-based applications. A product-based application is one that is packaged and made available for download in versions as a typical third-party product.

The architecture has a core set of operations that are used again and again in different patterns that depend upon the data and the task at hand.


### CI/CD

- ![image](https://github.com/kukuu/integration/assets/10147828/e06f4212-8d1e-4782-9a9c-2f11b8b54616)

### Kubernetes Orchestration

![image](https://github.com/kukuu/integration/assets/10147828/116fd731-8f01-4c0b-9f95-ed02d7bc726c)

###  Signing and Authenticating with JWT 
JSON Web Token (JWT) is a compact and self-contained way to represent information between two parties in a secure manner. It is often used for authentication and data exchange in web applications. JWTs are digitally signed, ensuring their integrity and authenticity. They consist of three parts: the header, the payload, and the signature.

It is a secure and compact way to transmit information between parties. It contains a header, payload, and signature, and can be created using symmetric or asymmetric encryption.


#### Features and Attributes of JWT

- Compact Format: JWTs are designed to be lightweight and compact, making them suitable for use in URLs, cookies, or HTTP headers
  
- Self-Contained: The token contains all necessary information to identify the user and verify the authenticity of the token.
  
- Signature: JWTs can be signed using a secret (symmetric) or unsigned using a public/private key pair (asymmetric) to ensure data integrity.
  
- Data Payload: The payload of a JWT can carry user information, claims, permissions, and more.
  
- Easy to Share: JWTs are easy to share across different services, making them useful in microservices architecture.

- Cross-Domain Communication: JWTs can be used to authenticate requests between different domains or systems.


#### Components of a JWT:

- - Header: Contains metadata about the type of token and the cryptographic algorithm used for signature verification.

- - Payload: Contains claims or statements about an entity (user) and additional data.

- - Signature: The encoded header, payload, and a secret key (for symmetric encryption) or private key (for asymmetric encryption) are used to create the signature, which verifies the integrity of the token.

#### Creating and Parsing JWT:

- Creation: To create a JWT, the header and payload are JSON-encoded, then concatenated with a secret key (for symmetric) or signed with a private key (for asymmetric). The result is the JWT token.

- Parsing: To parse and validate a JWT, the signature is verified using the provided secret key (symmetric) or public key (asymmetric). If the signature is valid, the data within the token can be extracted and used.


#### Symmetric vs. Asymmetric Encryption:
- Symmetric Encryption: In symmetric encryption, the same secret key is used for both encryption and decryption. It's faster but requires secure distribution of the key.

- Asymmetric Encryption: Asymmetric encryption uses a pair of keys: a public key for encryption and a private key for decryption. It eliminates the need for key sharing but is slower due to the complex mathematical operations involved.
![image](https://github.com/kukuu/integration/assets/10147828/409b7778-21df-4a6a-baa1-3186b6cada8b)



## Installing SSL Certificate

- Encryption: SSL provides encryption of data transmitted between a client and a server, ensuring confidentiality.

- Authentication: SSL authenticates the identity of the server using digital certificates, preventing impersonation and man-in-the-middle attacks.

- Data Integrity: SSL ensures that data is not tampered with during transmission.

- Trust and Security: SSL uses a certificate authority to verify the authenticity of a server's identity.

- Browser Compatibility: SSL certificates are widely supported by web browsers, ensuring seamless user experiences.
SEO Benefits: Google and other search engines give preference to HTTPS-enabled sites, improving search rankings.

- https://github.com/kukuu/digitalTransformationStrategies/tree/master/certificates

## OOP  Design Patterns

### The Constructor Design Pattern

The Constructor Design Pattern is a creational pattern used in software design to create objects by defining a constructor method in a class. It provides a blueprint for creating objects with specific properties and behaviors. This pattern is particularly useful when you want to ensure that an object is created with all the necessary attributes initialized properly. It promotes encapsulation and helps in managing object creation complexity, making it a fundamental part of object-oriented design and ensuring that objects are consistent and correctly configured from the start.

### The Module Design Pattern

JavaScript modules are the most prevalently used design patterns for keeping particular pieces of code independent of other components, and consistent. This provides loose coupling to support well-structured code.


For those that are familiar with object-oriented languages, modules are JavaScript "classes". One of the many advantages of classes is encapsulation - protecting states and behaviors from being accessed from other classes. The module pattern allows for public and private (plus the lesser-know protected and privileged) access levels.

Modules should be Immediately-Invoked-Function-Expressions (IIFE) to allow for private scopes - that is, a closure that protect variables and methods.

#### Revealing Module Pattern

A variation of the module pattern is called the Revealing Module Pattern. The purpose is to maintain encapsulation and reveal certain variables and methods returned in an object literal. The direct implementation looks like this.


### Prototype Design Pattern

 The Prototype design pattern relies on the JavaScript prototypical inheritance. The prototype model is used mainly for creating objects in performance-intensive situations.


 The objects created are clones (shallow clones) of the original object that are passed around. One use case of the prototype pattern is performing an extensive database operation to create an object used for other parts of the application. If another process needs to use this object, instead of having to perform this substantial database operation, it would be advantageous to clone the previously created object.


 To clone an object, a constructor must exist to instantiate the first object. Next, by using the keyword prototype variables and methods bind to the object's structure. Let's look at a basic example.

### Revealing Prototype Pattern

Similar to Module pattern, the Prototype pattern also has a revealing variation. The Revealing Prototype Pattern provides encapsulation with public and private members since it returns an object literal.

### Observer Design Pattern

There are many times when one part of the application changes, other parts needs to be updated. In AngularJS, if the $scope object updates, an event can be triggered to notify another component. The observer pattern incorporates just that - if an object is modified it broadcasts to dependent objects that a change has occurred.

Another prime example is the model-view-controller (MVC) architecture; The view updates when the model changes. One benefit is decoupling the view from the model to reduce dependencies.


### Publish/Subscribe

The Publish/Subscribe pattern, however, uses a topic/event channel that sits between the objects wishing to receive notifications (subscribers) and the object firing the event (the publisher). This event system allows code to define application-specific events that can pass custom arguments containing values needed by the subscriber. The idea here is to avoid dependencies between the subscriber and publisher.


Subscribers in the publish/subscribe pattern are notified through some messaging medium, but observers are notified by implementing a handler similar to the subject.

In AngularJS, a subscriber 'subscribes' to an event using $on('event', callback), and a publisher 'publishes' an event using $emit('event', args) or $broadcast('event', args).


### Singleton

A Singleton only allows for a single instantiation, but many instances of the same object. The Singleton restricts clients from creating multiple objects, after the first object created, it will return instances of itself.

Finding use cases for Singletons is difficult for most who have not yet used it prior. One example is using an office printer. If there are ten people in an office, and they all use one printer, ten computers share one printer (instance). By sharing one printer, they share the same resources.


In AngularJS, Singletons are prevalent, the most notable being services, factories, and providers. Since they maintain state and provides resource accessing, creating two instances defeats the point of a shared service/factory/provider.

Race conditions occur in multi-threaded applications when more than one thread tries to access the same resource. Singletons are susceptible to race conditions, such that if no instance were initialized first, two threads could then create two objects instead of returning and instance. This defeats the purpose of a singleton. Therefore, developers must be privy to synchronization when implementing singletons in multithreaded applications.


## Basic Programming Principles Programmers Should Follow

1. SOLID -The SOLID principles are a set of five design principles in software engineering that aim to create more maintainable, robust, flexible, extensible, and understandable code for object-oriented software systems and solve particular problems that might arise while developing software systems. Each principle focuses on a specific aspect of software design and encourages practices that lead to modular and well-structured code. The five SOLID principles are:


- Single Responsibility:  This principle states that a class should have only one reason to change. In other words, a class should have a single responsibility or job. This promotes high cohesion, where each class focuses on doing one thing well, making the code easier to understand, maintain, and extend.
  
- Open Closed: The Open-Closed Principle suggests that software entities (classes, modules, functions, etc.) should be open for extension but closed for modification. This means that you can add new functionality without modifying existing code. This is typically achieved through abstraction, inheritance, and polymorphism.
  
- Liskov Substitution: The Liskov Substitution Principle states that objects of a derived class should be able to replace objects of the base class without affecting the correctness of the program. In simpler terms, if a class is a subclass of another class, it should be able to be used interchangeably with the parent class without introducing unexpected behaviour.

- Interface Segregation: The Interface Segregation Principle suggests that clients should not be forced to depend on interfaces they don't use. In other words, interfaces should be specific and fine-grained, tailored to the needs of the implementing classes. This prevents classes from being burdened and overloaded with methods they don't need.

 
- Dependency Inversion: The Dependency Inversion Principle states that high-level modules should not depend on low-level modules; both should depend on abstractions. Additionally, abstractions should not depend on details; details should depend on abstractions. This promotes loose coupling and flexibility, allowing components to be easily replaced or extended without affecting the entire system.

Following these SOLID principles helps developers create more modular, maintainable, and adaptable software systems. By designing code with these principles in mind, developers can reduce code duplication, improve readability, and make future changes and additions to the codebase smoother and less error-prone.

They work in tandem with the 4 pillars of OOP: Encapsulation, Abstraction, Polymorphism, Inheritance

2. KISS. The “keep it simple, stupid” principle applies to pretty much all of life, but it's especially necessary for medium-to-large programming projects. 

3. DRY: Dont Repeat Yourself

4. Develop iteratively

5. Composition > Inheritance. 

6. Separation of Concerns. 

7. Avoid Premature Optimization.


## Further reading

- https://github.com/kukuu/integration
- https://github.com/kukuu/system-design-architecture/blob/master/README.md
- https://github.com/kukuu/integration/blob/main/jwt.md
- https://github.com/kukuu/AGILITY/raw/master/white-paper/JWT-architecture.png
- https://github.com/kukuu/Migration-of-Monolith-CMS-to-a-Headless-based-approach
- https://github.com/kukuu/high-volume-aws-cloud-mailingl-service-system
- 

