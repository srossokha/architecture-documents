#Web Application Architecture Review Checklist

##Design Considerations
* UI technology choice is based on application requirements and constraints
* Relevant presentation layer patterns are identified and used in the design
* The application is designed to separate rendering components from that manage presentation data and process
* Organization UI guidelines are well understood and addressed by the design
* The design is based upon knowledge of how the user wants to interact with the system

##Maintainability Considerations
* A suitable mechanism for manual and/or automatic updates to the application and its components is implemented taking into account versioning issues to ensure that the application has consistent and interoperable versions of all the components it uses.
* The appropriate deployment option is chosen depending on the presentation technology used.
* Components are designed to be interchangeable where possible, allowing change to individual components depending on requirements, runtime scenarios, and individual user requirements or preferences.
* Appropriate logging and auditing mechanism is implemented for the application to assist administrators and developers when debugging the application and solving runtime problems.
* Components and layers have minimal dependencies so that the application can be used in different scenarios where appropriate, without changes to other layers affecting the client application.

##Configuration Management
* Configurable data that may change in the life of the application is identified.
* The storage location has been identified, whether it should be stored locally or retrieved from elsewhere within the application.
* Global application settings are designed to be stored in a central location.
* Sensitive configuration information is protected when in memory, stored locally and in transit over the network.
* The design takes into account any global security policies that may affect or override local configurations.

##Caching
* Volatile data is not cached.
* Sensitive data is not cached unless absolutely necessary and encrypted.
* Data is cached is a ready to use format to reduce processing after the cached data is retrieved.
* Local caches uses IndexDB because of local storage limits.
* Service Workers are used instead of Cache Manifest for caching data on the client.

##Composition
* Dynamic layouts are avoided, when possible.
* Abstraction patterns are used to avoid dependencies between components.
* Composite View pattern is used if you need to compose views from modular, atomic components
* Publish/Subscribe pattern is used for communication between dynamically loaded modules.
* Command pattern is used to support menu and command-driven interaction.
* Observer pattern is used to decouple commands and navigation from the components in the application and to improve testability

##State Management
* The caching mechanism is designed considering the state information that the application must cache including estimates of the size, the frequency of changes, and the processing or overhead cost of recreating or re-fetching the data.
* The application uses IndexDB-based caching mechanism for storing large volumes of data.
* Data which needs to be available at application start-up is stored using a browser provided caching mechanism such us Cache Storage, Application Cache, IndexDB or LocalStorage

##Cookies.
* Sensitive cached data is protected using encryption and digital signatures
* Identified the granularity of the state information.
Exception Management
* Exceptions are not used to control logic flow.
* Exceptions are caught only if they can be handled.
* Global error handler is used to catch unhandled exceptions.
* User friendly messages are displayed when an exception or error occurs in the system. • Exception details do not reveal sensitive information.

##Data Services
* Translation is used to handle data formats that are not supported by the client application.
* Large data sets are chunked and loaded asynchronously into a local cache to improve performance.
* UI responsiveness is maximized by loading data asynchronously when possible.
* A service dispatcher mechanism is used to monitor connectivity and send batched updates when a suitable connection is available.
* Concurrency conflicts are detected and managed using either optimistic or pessimistic models.

##Input
* Accessibility was considered in the design.
* Localization was considered in the design

##Layout
* Templates are used to provide a common look and feel.
* A common layout is used to maximize accessibility and easy to use.
* The layout considers device-independent input, such as touch screens, inc, or speech • Cascading Style Sheets are used wherever possible for layout

##Navigation
* Navigation is separated from UI processing.
* Toolbars and menus are designed to help users find functionality provided by the UI.
* Wizards are used to implement navigation between firms in a predictable way.
* If navigation state is needed across sessions, the application is designed to persist navigation state.
* Command pattern is used to handle common actions from multiple sources.

##Presentation Entities
* Presentation entities are used only if you need to manage unique data or data formats in the presentation layer.
* Presentation entities do not contain business logic.
* Custom classes are used to map data directly to business entities.
* Presentation entities contain input validation logic for the presentation layer.

##Request Processing
* Requests do not block the UI.
* Long running requests are identified in the design and optimized for UI responsiveness.
* UI request processing are unique components and are not mixed with components that
render the UI or components that instantiate business rules.
* Passive View pattern is used to design interfaces that not manage a lot of data.
* Supervising Controller pattern is used for interfaces that manage large amounts of data.

##User Experience
* UI responsiveness is considered in the design. For instance, rich clients don’t block UI threads and Rich Internet applications avoid synchronous processing.
* AJAX, Sockets or MQTT are used if you are building a web application and user responsiveness is important.
* The design has identified key user scenarios and has made them as simple to accomplish as possible.
* The design supports personalization, localization, and accessibility.
* The design empowers users, allowing them to control how they interact with the application and how it displays data.

##UI Components
* Component has one reason to change (Single Responsibility Principle).
* Component provides props to control its behavior while not exposing its internal structure
* Component is compassable and could be created from the composition of smaller specialized components
* Component is reusable, written ones but used multiple times.
* Component is pure or almost-pure. Pure component always renders same elements for same props. Almost-pure component always renders same elements for same prop values, and can produce a side effect.
* Component is meaningful. Its easy to understand what it does.

##UI Processing Components
* UI process components are created only when necessary
* If the UI requires complex processing, UI processing has been decoupled from rendering and display into unique UI processing components
* If the UI requires complex workflow support, the design includes unique workflow components that use a workflow system.
* UI processing components do not include business rules.
Validation
* The application constrains, rejects and sanitizes all input that comes from the client.
* Server-side validation is used to validate input for security purposes.
* Client-side validation is used to validate input for user experience purposes, for instance to give the user error messages after receiving poor input.
* AJAX, Sockets are used in Web applications to provide real-time validation.
* Validation routines are centralized, where possible, to improve maintainability and reuse. 

##Offline / Occasionally Connected Considerations
* Asynchronous communication is used whenever possible for interacting with data and services over a network.
* Complex interactions with network-located data and services are minimized or eliminated.
* Data caching is designed to ensure that all of the data necessary for the user to continue working is available on the client when it goes offline.
* A mechanism to manage connections is designed that takes into account the environment in which your application operates, both in terms of the available connectivity and the desired behavior of your application as this connectivity changes.
* A store-and-forward mechanism is designed for communication so that messages are created, stored while the application is disconnected, and forwarded to their respective destinations when a connection becomes available.

##Deployment Considerations
* The target physical deployment environment is identified, early in the planning stage of the design lifecycle.
* Environmental constraints that may impact your software design and architecture decisions are identified.
* Aspects of the software design that require certain infrastructure attributes are identified.