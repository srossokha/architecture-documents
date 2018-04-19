#Architecture Review

##General Design Considerations
* Areas of concern are separated.
* Every component has a single responsibility.
* Components do not rely on the internal details of other components. 
* Functionality is not duplicated within the application.
* Components are grouped logically into layers.
* Abstraction is used to design loose coupling between layers.

##Authentication
* Trust boundaries have been identified, and users are authenticated across trust boundaries.
* Single sign-on is used when there are multiple systems in the application.
* Passwords are stored as a salted hash, not plain text.
* Strong passwords or password phrases are enforced.
* Passwords are not transmitted in plain text.

##Authorization
* Trust boundaries have been identified, and users are authorized across trust boundaries.
* Resources are protected with authorization on identity, group, claims or role.
* Role-based authorization is used for business decisions.
* Resource-based authorization is used for system auditing.
* Claims-based authorization is used for federated authorization based on a mixture of information such as identity, role, permissions, rights, and other factors.

##Caching
* Volatile data is not cached.
* Data is cached in ready to use format.
* Unencrypted sensitive data is not cached.
* Transactional resource manager or distributed caching is used, if your application is deployed in Web farm.
* Your application does not depend on data still being in cache.

##Communication
* Interfaces support chunky communication to reduce calls.
* Unmanaged code is used for communication across AppDomain boundaries.
* Message-based communication is used when crossing process or physical boundaries.
* Processing threads use asynchronous communication.
* Message queuing is used for reliable messaging.
 
##Composition
* Dynamic layouts are not used, if they need to be used maintenance tradeoff are considered.
* Abstraction is used between components to improve maintainability.
* Template View pattern is used, to improve reuse and consistency of dynamic web pages.
* Composite View pattern is used to compose views from modular atomic parts.

##Concurrency and Transactions
* Business-critical operations are wrapped in transactions.
* Connection-based transactions are used in the case of a single data source.
* Transaction Scope (System.Transaction) is used in the case of multiple data sources.
* Compensating methods are used to revert the data store to its previous state when transactions are not used.
* Locks are not held for long periods during long-running atomic transactions.

##Configuration Management
* Least-privileged process and service accounts are used.
* All the configurable application information is identified.
* Sensitive information in the configuration is encrypted.
* Access to configuration information is restricted.
* If there is a configuration UI, it is provided as a separate administrative UI.

##Coupling and Cohesion
* Application is partitioned into logical layers.
* Layers use abstraction through interface components, common interface definitions, or shared abstraction to provide loose coupling between layers.
* The components inside layers are designed for tight coupling, unless dynamic behavior requires loose coupling.
* Each component only contains functionality specifically related to that component.
* The tradeoffs of abstraction and loose coupling are well understood for your design. For instance, it adds overhead but it simplifies the build process and improves maintainability.

##Data Access
* Database schema is not coupled to your application model.
* Connections are opened as late as possible and released quickly.
* Data integrity is enforced in the database, not in the data access layer.
* Business decisions are made in the business layer, not the data access layer.
* Database is not directly accessed; database access is routed through the data access layer.
* Resource gateways are used to access resources outside the application.

##Exception Management
* Exceptions are only caught where they can be handled.
* Sensitive information is not included in exception messages or log files.
* There is a design for exception propagation.
* There is a strategy for handing unhandled exceptions.
* There is a strategy for logging exception information.
* Users are notified when there are critical errors and exceptions.

##Layering
* Layers represent a logical grouping of components. For example, use separate layers for user interface, business logic, and data access components.
* Components within each layer are cohesive. For example, the business layer components should provide only operations related to application business logic.
* When communication between layers crosses a physical tier, message-based operations are used.
* When communication does not cross a physical boundary, object-based operations are used.
* If testability is important, an Interface type has been defined for the interfaces in each layer.

##Logging and Instrumentation
* There is a centralize logging and instrumentation mechanism.
* System events and critical business events are instrumented.
* The design includes a strategy for passing audit and log information across tiers. • Log files are secured against unauthorized access.
* Sensitive information is not stored in log files.

##State Management
* The only data persisted is what’s necessary to maintain state.
* State is serialized if it needs to be persisted or shared across the network.
* Basic types are used for session data to reduce the serialization cost. * Session state communication channel is protected.

##Structure
* Your design is based on a common application structure such as Client/Server or N-Tier.
* Deployment environment security requirements are well understood. For example, many security policies require physical separation of presentation logic from business logic across different sub-nets.
* Scalability and reliability requirements are well understood for your application.
* Deployment scenarios are well understood for your application.

##User Experience
* The design includes a consistent navigation experience. For example, composite patterns for the look-and-feel, and controller patterns such as MVC, Supervising Controller, and Passive View, for UI processing.
* Each page or section is focused on a specific task.
* Similar UI components have consistent behavior across the application. For example, a grid used to display data should be displayed and used consistently throughout the application.
* UI screens are not overloaded.

##Validation
* Trust boundaries are identified, and all the inputs are validated when they cross the trust boundary.
* A centralized validation approach is used.
* Validation strategy constrains, rejects, and sanitizes malicious input.
* Input data is validated for length, format, and type.
* Client-side validation is used for user experience and server-side validation is used for security.

##Workflow
* Workflow management requirements are well understood.
* There is a strategy for handling workflow exceptions.
* Service interfaces are used to interact with external workflow providers. 
* Designers and metadata are used, where possible, to define workflow.