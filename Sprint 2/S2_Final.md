# Business Questions (BQs)

For each BQ, we developed a Dashboard with LookerStudio. These reports contain relevant visualizations that allow StakeHolders to answer the BQ of their interest. Details regarding the implementation of the analytics engine, as well as relevant links to access these reports, are available at the [Analytics Pipeline](https://github.com/ISIS3510-202410-Team-13/Analytics) repository.

## BQ 2.1 (Type 2)

_Developed by: Juan Cuellar_

**Question:**
What is the mean User Satisfaction Score regarding the ease of use and the availability of spaces provided by the app's space booking feature?

**Justification:**
This question aims to directly enhance the user experience by identifying any difficulties users may encounter while navigating the app, particularly when booking spaces for meetings. Understanding these challenges allows for immediate improvements in the app's interface and functionality, ensuring a smoother booking process. The feedback can be used to refine the app's design, making daily interactions more intuitive and satisfying for users.

**Note:**
Within the Sprint 1 feedback we were asked to revise the structure of the first and last Type 2 BQs to present only a single question instead of two. Hence, here we have picked the first part of that question to implement.

**[Analytics Pipeline Implementation:](https://lookerstudio.google.com/reporting/1af52a7c-94e9-4970-ad3f-76ac91c16c24/page/w0vtD)**

<img width="1202" alt="image" src="https://github.com/ISIS3510-202410-Team-13/Wiki/assets/68788933/e739440a-7280-4eea-ae68-f3a0d9d0ed08">

## BQ 2.3 (Type 2)

_Developed by: Juan Castellanos_

**Question:**
How does the integration of social features within UniSchedule, like schedule sharing and group event planning, influence user retention and daily active usage?

**Justification:**
This question is aimed at understanding how social features within the app enhance the daily user experience by facilitating easier coordination and engagement among students. It directly relates to improving user interaction with the app, making it more valuable and user-friendly, which is central to enhancing direct user experience.

**[Analytics Pipeline Implementation:](https://lookerstudio.google.com/reporting/9281694c-2631-46f5-8aab-0b23cb568ee9/page/ZLwtD)**

<img width="1201" alt="image" src="https://github.com/ISIS3510-202410-Team-13/Wiki/assets/68788933/5868c123-8d15-4612-afd3-9f6590a93d26">


## BQ 3.4 (Type 3)

_Developed by: Laura Arias_

**Question:**
Which schedule customization features in UniSchedule are underutilized or not utilized by the users in the last semester?

**Justificaction:**
This question is categorized under Type 3 because it directly focuses on assessing the utility and relevance of specific features within the app. By identifying which schedule customization features are less used or ignored by the users, the business can gain valuable insights into which features might need improvements, redesign, or even removal

**[Analytics Pipeline Implementation:](https://lookerstudio.google.com/reporting/d9c878b6-38cf-4186-ac6f-20c4ac3192ce/page/57wtD)**

> Keep in mind that we designed some Dashboards in Spanish on purpose because some of our potential Stakeholders might not speak English

<img width="1202" alt="image" src="https://github.com/ISIS3510-202410-Team-13/Wiki/assets/68788933/99855a48-bb79-47f1-bc6f-3dac11edcfbb">


## BQ 4.1 (Type 4)

_Developed by: David Ortiz_

**Question:**
What is the average weekly usage time per user within UniSchedule, and which specific section of the app engages users the longest for placing advertisement?

**Justificaction:**
This question is classified as Type 4 because it focuses on understanding user engagement metrics within the app, such as average usage time and most visited sections, with the aim of leveraging this data for monetization purposes. By identifying the sections of the app where users are most active, the business can optimize advertisement placements to ensure maximum visibility and engagement, thereby enhancing the value proposition for potential advertisers.

**[Analytics Pipeline Implementation:](https://lookerstudio.google.com/reporting/fb3c5144-378b-4239-a3df-c5327648dbe9/page/eovtD)**


![image](https://github.com/ISIS3510-202410-Team-13/Wiki/assets/78111224/abea4da5-9165-4d47-8be5-f2f2d325b505)


## BQ 5.2 (Type 5)

_Developed by: Juan Urrea_

**Question:**
What are the preferred times and locations for users to hold their meetings?

**Justification:**
This question serves a dual purpose (Type 2 and 4).
1. Firstly, it aims to improve the user experience by understanding users' preferences regarding meeting times and locations. By identifying the most convenient and popular times and places for meetings, the app can offer tailored recommendations and optimize its scheduling features to better meet users' needs, ultimately enhancing user satisfaction and engagement. 
2. Secondly, this question explores the potential for monetization by leveraging the collected data on users' meeting preferences. By analyzing this data, the app can provide valuable insights to Los Andes University, such as peak times for space utilization and preferred meeting locations. This information can be utilized by the university to optimize resource allocation, improve campus facilities, and enhance the overall campus experience for students. Through partnerships with the university, the app can monetize this data by offering valuable analytics services or by facilitating targeted advertising opportunities to relevant stakeholders within the university community.

**[Analytics Pipeline Implementation:](https://lookerstudio.google.com/reporting/cfd155a3-f15c-40dc-8a40-ac8b716ae167/page/WPxtD)**

<img width="1204" alt="image" src="https://github.com/ISIS3510-202410-Team-13/Wiki/assets/68788933/a6f903b7-c208-4bf9-aa29-1fff8328c606">


# Analytics Pipeline (AP)
## Design of the Analytic Pipeline
_Essential Diagram_
![Analytics Pipeline - Final](https://github.com/ISIS3510-202410-Team-13/Wiki/assets/53950946/64d172a1-76c8-4ce7-85b3-6948ccfea569)

_Detailed Diagram - Specific components_
![Specified Analytics Pipeline](https://github.com/ISIS3510-202410-Team-13/Wiki/assets/72948114/f8a65ffe-b76f-4e56-837b-b01c72c83e30)


## Description of the Analytic Pipeline

**1. Data source:**
The main data will be coming from:  
- Analytics data (user behavior data) as we want to know is the user preferences. 
- Transactional data, data from sales or what adds produce the most value for the app. 
- 3rd party data (data your company doesn’t collect directly but uses) this is mainly to compare our app with other apps so we can improve the app.  


**2. Data Ingestion:**
We will implement mechanisms to capture data efficiently and securely. This could include integrations with the application’s database, as well as capturing events through API’s (such as course offerings) or event registration services. 

**3. Data processing:**
To process data we need to think in a  ELT we have the data source, then the Extract (clean data) focus on the database (schema creation, Mapping, Automatization) into the data warehouse and then to the transformation. 

**4. Data storage:**
The processed data will be stored in a suitable database for efficient access and query. This could be a relational database like PostgreSQL or a NoSQL database like cloud Firestone, depending on our data structure and query needs that we haven’t defined yet. 

**5. Data Consumption:**
analytics across the business for all users through purpose-built analytics tools that support analysis methodologies such as SQL, batch analytics, reporting dashboards. In this case we are going to use an analytics batch.

**6. Data Governance and security:**
We will implement measures to ensure data security and privacy. This could include user authentication, encryption of data at rest and in transit, and compliance with data protection regulations such as GDPR (EU General Data protection Regulation) or other local regulations. 

# Architectural design (AD)

## Context Diagram

![UniSchedule - Context](https://github.com/ISIS3510-202410-Team-13/Wiki/assets/68788933/5aaaee44-ba85-4d98-adab-ee7d5f278cd7)

The context diagram illustrates the broader ecosystem in which UniSchedule operates, showcasing the interactions and dependencies between various components and external entities. This high-level overview provides insights into how UniSchedule interacts with different stakeholders and systems to deliver its functionality effectively.

### Components and External Services:

#### Android/iOS Clients:

Android and iOS mobile applications serve as the primary interfaces for end-users to interact with UniSchedule's features and functionalities. These clients connect directly to the UniSchedule Backend to access and manipulate data, manage schedules, and receive updates.

#### UniSchedule Backend:

The central hub of information and functionality, the UniSchedule Backend, serves as the backbone of the entire system. It facilitates communication between the mobile clients, Analytics Engine, and external services, orchestrating data retrieval, storage, and processing. The backend is connected to various databases and external APIs to support its operations effectively.

#### Analytics Engine:

The Analytics Engine consumes data from the UniSchedule Backend to generate insightful visualizations and analytics, providing users with valuable insights into their scheduling patterns, productivity trends, and more. While the Analytics Engine relies on the backend for data access, it remains independent of the underlying data models through a facade pattern, ensuring modularity and maintainability.

#### Analytics Dashboard:

The Analytics Dashboard serves as the user interface for accessing and interacting with the analytics and visualizations generated by the Analytics Engine. Users can view charts, graphs, and reports that offer insights into their scheduling habits and productivity metrics.

#### External Services:

UniSchedule interacts with various external services to enhance its functionality and provide comprehensive features to users:

- Uniandes Courses API: Provides data on course schedules and availability, assisting in determining classroom availability at any given time.
- Native Calendar Apps: Syncs with popular calendar applications like Google Calendar, Apple Calendar, and Microsoft Calendar to ensure seamless integration and synchronization of events and schedules.
- Email Platforms and Messaging Apps: Facilitates sending invitations and notifications to users via email and messaging platforms, ensuring effective communication and event coordination.

### Databases:

#### Locations Database:

Stores information about available spaces on the campus, enabling UniSchedule to identify and recommend suitable meeting places based on user preferences and availability.

#### Users Database:

Saves authentication information, user preferences, friend connections, and other user-related data to personalize the UniSchedule experience for each user.

#### Events Database:

Manages recurring classes, one-time events, and other schedule-related information, ensuring accurate tracking and management of user schedules.

#### Chat Database:

Stores data related to the chat feature, including message history, user interactions, and group conversations, facilitating seamless communication between users.

#### Groups Database:

Manages collections of users, group events, preferences, and membership details, supporting collaborative scheduling and group activities within UniSchedule.

#### Telemetry Database:

Records information about feature usage, bugs, crash reports, user input events, and other telemetry data, enabling continuous improvement and optimization of the UniSchedule application.

### Interaction Patterns:

#### Mobile Clients <-> UniSchedule Backend:

Mobile clients interact directly with the UniSchedule Backend to perform various actions such as accessing schedules, creating events, managing tasks, and receiving notifications. All external requests from mobile clients are handled through the backend, ensuring a unified, secure and consistent interface for data access and manipulation.

#### Analytics Engine <-> UniSchedule Backend:

The Analytics Engine consumes data from the UniSchedule Backend to generate visualizations and analytics. However, it interacts with the backend through a facade pattern, abstracting the underlying data models to maintain independence and modularity, instead of directly querying the databases.

## Backend Components Diagram

![UniSchedule - Components](https://github.com/ISIS3510-202410-Team-13/Wiki/assets/68788933/03d6879f-bdd0-414f-9fd0-6c9b9bbd9e02)

The Backend Components Diagram illustrates the internal microservices that constitute the backend architecture of UniSchedule. Each microservice is responsible for specific features and interacts with external services and databases to fulfill its functionalities effectively.

### AvailableSpaces Service

- **Purpose**: Fetches data from the external Uniandes Courses API and saves it in the Locations Database to calculate available spaces on campus.
- **Interactions**:
  - Reads data from Uniandes Courses API.
  - Writes data to Locations Database.
- **Functionality**: Determines available spaces on campus based on course schedules.

### ImportBindings Service

- **Purpose**: Implements an adapter pattern to fetch data from different external services for native calendar apps and email platforms.
- **Interactions**:
  - Fetches data from various external services for native calendar apps and email platforms.
- **Functionality**: Integrates data from external platforms into UniSchedule backend.

### Sharing Service

- **Purpose**: Sends data to messaging apps to enable schedule sharing services.
- **Interactions**:
  - Sends data to messaging apps.
- **Functionality**: Facilitates sharing schedules with other users via messaging apps.

### User Authentication Service

- **Purpose**: Handles user authentication processes.
- **Interactions**:
  - Reads and writes data to Users Database.
- **Functionality**: Manages user authentication and authorization.

### Profile Service

- **Purpose**: Reads and writes data to Users Database to manage user profiles.
- **Interactions**:
  - Reads and writes data to Users Database.
- **Functionality**: Manages user profiles and preferences.

### Friends Service

- **Purpose**: Reads and writes data to Users Database to handle features related to user friendships.
- **Interactions**:
  - Reads and writes data to Users Database.
- **Functionality**: Manages user friendships and connections.

### Groups Service

- **Purpose**: Reads and writes data to Groups Database to handle features related to groups such as creation, adding/removal of members, etc.
- **Interactions**:
  - Reads and writes data to Groups Database.
- **Functionality**: Manages groups and group-related features.

### Events Service

- **Purpose**: Reads and writes data from Events Database and handles features related to event creation.
- **Interactions**:
  - Reads and writes data from Events Database.
  - Invokes ImportBindings and Sharing Services for integration with other platforms.
- **Functionality**: Manages events and event-related features.

### Crash Reports Service, Bug Reports Service, and Tally Metrics Service

- **Purpose**: Read and write to Telemetry Database to handle features related to improving user experience, bug detection, app monitoring, etc.
- **Interactions**:
  - Reads and writes data to Telemetry Database.
- **Functionality**: Manages telemetry data and analytics for app performance and user experience improvement.

### Chat Service

- **Purpose**: Reads and writes to Chat Database and handles chat-related features between users or in groups.
- **Interactions**:
  - Reads and writes data to Chat Database.
- **Functionality**: Manages chat-related features and interactions.

### Notifications Broadcaster

- **Purpose**: Sends server-based push notifications to users when they receive new messages.
- **Interactions**:
  - Utilizes Chat Service to determine new message notifications.
- **Functionality**: Sends notifications to users for new chat messages.

### Mobile Frontend General Architecture

The mobile frontend architecture of UniSchedule consists of four layers: Presentation, Application, Domain, and Infrastructure. Each layer provides different services and interacts with the backend in a sequential manner to fulfill user requests and provide a seamless user experience.

- **Presentation Layer**: Responsible for interacting with the user interface, capturing user inputs, and displaying information back to the user.
- **Application Layer**: Serves as a conduit between the Presentation Layer and the Domain Layer, orchestrating data flow and directing application tasks based on user inputs.
- **Domain Layer**: Represents the core business logic and domain knowledge of UniSchedule, encapsulating business concepts, rules, and logic.
- **Infrastructure Layer**: Supports the other layers by providing technical capabilities such as persistence mechanisms, communication with external services, and other utilities.

The backend and frontend are mediated by an API gateway to enhance security and scalability, ensuring efficient communication and interaction between the two layers.

## Domain-Driven Design Diagram

![dominiosegunsnow drawio (2)](https://github.com/ISIS3510-202410-Team-13/Wiki/assets/78111224/ac2dcd58-64f7-41b7-a9c1-e2833417ae0f)


This diagram focuses on modeling software to match a complex domain or business. The structure of the software is aligned with the domain it aims to serve, emphasizing a deep connection between the software's design and its underlying business model. The approach is typically divided into four main layers, each with a specific responsibility and role within the software architecture. These layers ensure that the domain logic remains isolated from other concerns such as the user interface, external integrations, and data persistence.

### 1. Presentation Layer

- **Purpose**: The Presentation Layer is responsible for interacting with the user. It captures user inputs and displays information back to the user.
- **Components**: This layer includes components like pages, widgets, and the mechanisms for the communication between them. It's where the user interface (UI) resides.
- **Responsibilities**: Its main responsibilities include input validation, user session management, and UI logic, ensuring a seamless user experience that accurately represents the underlying domain models.

### 2. Application Layer

- **Purpose**: The Application Layer serves as a conduit between the Presentation Layer and the Domain Layer. It orchestrates the flow of data to and from the domain, and directs the application's tasks based on user inputs.
- **Components**: This layer consists of application services, which encapsulate the business use cases of the application. It might also include event handlers and application-level validation.
- **Responsibilities**: It handles the application's workflow, enforces application-wide rules, and coordinates domain objects to perform specific tasks. This layer does not contain business logic itself but controls the application logic.

### 3. Domain Layer

- **Purpose**: The Domain Layer is the heart of the DDD approach, where the core business logic and domain knowledge are encapsulated.
- **Components**: This layer comprises domain entities, value objects, domain events, aggregates, and domain services. These elements model the business concepts, rules, and logic.
- **Responsibilities**: The Domain Layer is tasked with representing concepts of the business, information about the business situation, and business rules. State that reflects the business situation is controlled and used here, even though the technical details of storing it are delegated to the Infrastructure Layer.

### 4. Infrastructure Layer

- **Purpose**: The Infrastructure Layer supports the other layers by providing technical capabilities such as persistence mechanisms, implementations of the repository interfaces defined in the Domain Layer, and other utilities such as message sending or receiving.
- **Components**: This layer includes repositories, data access objects (DAOs), and other services that are required to connect the application to its external dependencies like databases, file systems, and third-party services.
- **Responsibilities**: Its primary responsibility is to communicate with external resources and perform data storage and retrieval operations. It translates domain models to and from the data models used by databases, ensuring that the domain model remains persistent agnostic.

Each layer has its distinct role, ensuring a separation of concerns that facilitates a maintainable, scalable, and adaptable system. This layered architecture promotes a clean separation between the software's business logic and its technical aspects, allowing for flexibility and ease of development and maintenance.


## Class Diagram

![negociosegunurri drawio](https://github.com/ISIS3510-202410-Team-13/Wiki/assets/78111224/f4bd2751-5c80-45bc-9435-7d39b5ec4e26)

The diagram leverages a combination of design patterns to create a robust, scalable, and maintainable architecture. Below is a detailed explanation of the architecture, focusing on the Singleton, Facade, and Observer patterns adapted with Riverpod for state management.

### Singleton Pattern: ScheduleManagementFacade

- **Purpose**: The Singleton pattern is utilized in the `ScheduleManagementFacade` class to ensure there is only a single instance of this class throughout the application's lifecycle. This approach is critical for centralizing and managing access to various scheduling-related services and functionalities.

- **Implementation**: `ScheduleManagementFacade` is designed as a Singleton to provide a unified access point to the application's core functionalities, such as event scheduling, task management, and notifications. By maintaining a single instance, the application ensures consistent and synchronized operations across different parts of the system.

### Observer Pattern Adapted with Riverpod (Providers)

- **Purpose**: Adapting the Observer pattern with Riverpod allows the application to efficiently manage state and facilitate communication between the UI components (widgets) and the application's state. Providers in Riverpod act as observable subjects, notifying subscribed widgets of state changes, which leads to reactive UI updates.

- **Implementation**:
  - **ScheduleProvider**: Manages the state related to users' schedules and calendar events. Widgets subscribing to this provider will re-render to reflect updates in the schedule.
  - **TaskProvider**: Handles the tasks' state, including adding, removing, and listing tasks. Widgets connected to this provider update as the task list changes.
  - **NotificationProvider**: Manages notification state, enabling widgets to display the latest notifications as they are added or removed.
  - **ProductivityProvider**: Analyzes and provides insights on productivity patterns. Widgets listening to this provider present productivity analytics and recommendations.
  - **SocialFeaturesProvider**: Facilitates social interactions within the app, like viewing friends' schedules and planning group events. Widgets utilizing this provider update based on social features' state changes.

### Facade Pattern: ScheduleManagementFacade

- **Purpose**: The Facade pattern is employed through the `ScheduleManagementFacade` to offer a simplified and cohesive interface to complex subsystems within the application, such as scheduling events, managing tasks, and handling notifications. This pattern enhances usability and maintainability by encapsulating the complexities of interactions with various subsystems.

- **Implementation**: The `ScheduleManagementFacade` provides high-level methods that internally use the Riverpod providers to perform operations. This setup simplifies the interaction with the application's functionalities for the client components, ensuring that complex sequences of actions can be executed with simple method calls.

### Detailed Widget-Provider Connections

Each provider is connected to multiple widgets, ensuring a dynamic and reactive user interface:

- **ScheduleProvider**:
  - Connected to `ScheduleWidget` for displaying user schedules.
  - Connected to `EventDetailsWidget` for showing and editing specific event details.

- **TaskProvider**:
  - Connected to `TaskListWidget` for listing user tasks.
  - Connected to `TaskDetailWidget` for viewing and managing details of individual tasks.

- **NotificationProvider**:
  - Connected to `NotificationWidget` for showing current notifications.
  - Connected to `NotificationSettingsWidget` for adjusting notification preferences.

- **ProductivityProvider**:
  - Connected to `ProductivityWidget` for displaying productivity insights.
  - Connected to `GoalSettingWidget` for setting and tracking productivity goals.

- **SocialFeaturesProvider**:
  - Connected to `SocialWidget` for managing and viewing social interactions.
  - Connected to `FriendListWidget` for listing friends and their schedules.
  - Connected to `EventPlanningWidget` for coordinating group events.

This architecture ensures that the UniSchedule app remains adaptable, with each component focused on a specific responsibility, leading to cleaner code, easier debugging, and enhanced user experience.



## Deployment Diagram

![UniSchedule - Despliegue](https://github.com/ISIS3510-202410-Team-13/Wiki/assets/69651671/da126104-26b5-4345-b3ac-7e1eb82a5e3e)

The diagram depicted represents a deployment diagram for UniSchedule, crafted to exhibit the distribution and communication of software artifacts across the physical infrastructure. In this case, the diagram demonstrates a distributed system utilizing cloud services, specifically the Google Cloud Platform (GCP), to host application servers and database systems. This arrangement not only defines the environment in which the UniSchedule application will operate but also reflects a series of deliberate design decisions and architectural patterns selected to optimize performance, scalability, availability, security, and maintainability of the application.

### Description of the diagram

* **Device Layer:**

   * The application is intended to run on an Android device, which indicates a decision to use the Android platform's features and the Android SDK for development.
   * A separate cache memory is used to improve performance by storing frequently accessed data locally also for eventual connectivity.

* **Application Layer:**

   * The UniSchedule application is the front-end that users interact with

* **Server and Backend Systems:**

   * The architecture includes application servers hosted on Google Cloud Platform (GCP), indicating a choice for cloud services for scalability and reliability.

   * Cloud Load Balancing is in place, it's an strategy to manage traffic effectively and ensure availability.

   * The Backend is separated from the Application Server, following a microservices architecture pattern for modularity and maintainability.

* **External APIs:**

   * Integration with various external APIs like Auth0 for authentication, Calendar APIs, Location APIs, and a university-specific Courses API implies an extensible and modular system that can interface with various services to provide comprehensive functionality.

* **Database Systems:**

   * Multiple databases for users, locations, groups, events, telemetry, and chat highlight a decision to segregate data logically for better management, security, and performance.

   * The presence of separate application servers for different database systems on GCP shows a distributed system approach which enhance scalability and fault tolerance.

* **Services:**

   * Services such as Data Preparation, Data Target Storage, and Analytics & BI (Business Intelligence) suggest the use of data warehousing and data analytics patterns to process, store, and analyze data, which can provide insights and support data-driven decisions.


### Architectural Tactics

* **Performance**: Use of caching and load balancing.
* **Scalability**: Cloud hosting and distributed database systems.
* **Availability**: Load balancing and cloud infrastructure.
* **Security**: Auth0 for authentication.
* **Modifiability**: Microservices architecture with separate backend systems.
* **Interoperability**: Use of external APIs for extended functionality.

# List of implemented features (IF)

> You can find the implementation of the App with [Kotlin](https://github.com/ISIS3510-202410-Team-13/Kotlin) and [Flutter](https://github.com/ISIS3510-202410-Team-13/Flutter) in their respective repositories. 

> We grouped features into more general functionalities that implemented 1 or more features at the same time.

> You might find text in Spanish in the following demos. Worry not! We fixed it in [Kotlin](https://github.com/ISIS3510-202410-Team-13/Kotlin/pull/13) and [Flutter](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/40) for the App release.

| **#** |                 **Type of Functionality**                 |               **Functionality**              |
|:-----:|:---------------------------------------------------------:|:--------------------------------------------:|
|   1   | Functionality that uses at least one sensor in the phone. |          Biometrical Authentication          |
|   2   |        Functionality that answers type 2 questions.       | Meeting place recomendation<br>User Feedback |
|   3   |            Functionality that is context aware.           |              Event Notification              |
|   4   |      Functionality that is considered smart features.     |         Meeting place recommendation         |
|   5   |      Functionality that allows users authentication.      |          Biometrical Authentication          |
|   6   |         Functionality that uses external services.        |         Meeting place recommendation         |

## Functionality 1: Biometrical Authentication

This functionality utilizes at least one sensor in the phone, such as fingerprint or facial recognition technology, to authenticate users. Biometric authentication offers a secure and convenient way for users to access the application without the need for traditional password-based authentication.

**Related:** [Flutter#22](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/22) - [Kotlin#10](https://github.com/ISIS3510-202410-Team-13/Kotlin/pull/10)

https://github.com/ISIS3510-202410-Team-13/Wiki/assets/68788933/1682bc3b-ebc0-437f-9034-4a16484f0ee6


## Functionality 2: Event Notification

This functionality provides users with notifications about upcoming events or important updates within the application. Users receive timely alerts and reminders, ensuring they stay informed about their schedules and any relevant changes or additions.

**Related:** [Flutter#32](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/32) - [Flutter#29](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/29) - [Kotlin#14](https://github.com/ISIS3510-202410-Team-13/Kotlin/pull/14)

https://github.com/ISIS3510-202410-Team-13/Wiki/assets/68788933/108ae367-b448-4c01-8d5d-cc52cb8fa1cb


## Functionality 3: Meeting Place Recommendation

This functionality utilizes the AvailableSpaces service provided by our backend to recommend suitable meeting places based on user preferences and availability. The AvailableSpaces service retrieves information about available spaces within specified time frames and days of the week at the campus of Universidad de los Andes. By integrating our mobile frontend with this external data source, our application can leverage smart algorithms to generate personalized recommendations that optimize convenience and accessibility for user meetings. The service implementation and detailed documentation is available at the [Backend Services](https://github.com/ISIS3510-202410-Team-13/Backend) repository.


**Related:** [Flutter#34](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/34) - [Flutter#26](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/26) - [Backend#2](https://github.com/ISIS3510-202410-Team-13/Backend/pull/2)

https://github.com/ISIS3510-202410-Team-13/Wiki/assets/68788933/b256b583-d4bf-4137-b5c1-8fc6e7f828d4

## Functionality 4: User Feedback

This functionality allows users to provide feedback on a crucial aspect of the application: the available spaces recommendation system. User feedback is essential for continuous improvement, helping the development team identify areas for enhancement and prioritize future updates to enhance the user experience.

**Related:** [Flutter#36](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/36)

https://github.com/ISIS3510-202410-Team-13/Wiki/assets/68788933/7e9d607a-3311-474b-855a-cd9de51a81e1


# Table of Implemented Views

> You might find text in Spanish in the following demos. Worry not! We fixed it in [Kotlin](https://github.com/ISIS3510-202410-Team-13/Kotlin/pull/13) and [Flutter](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/40) for the App release.

| Auth | Home | Calendar | Add-Event |
|:------:|:------:|:------:|:------:|
| ![Auth](https://github.com/ISIS3510-202410-Team-13/Wiki/assets/68788933/b28a4171-a03e-4188-a7e4-a75b6e9541aa) | ![Home](https://github.com/ISIS3510-202410-Team-13/Wiki/assets/68788933/0f5e8c4e-5267-46cc-8599-568876086ac4) | ![Calendar](https://github.com/ISIS3510-202410-Team-13/Wiki/assets/68788933/698fa3b8-a98f-40ce-a4cb-09a93e806a4c) | ![Add-Event](https://github.com/ISIS3510-202410-Team-13/Wiki/assets/68788933/cf465ef9-51d1-4924-8b0f-b0a3153cd1ff) |

# Ethics Video

[Ethics Video Sprint 2](https://youtu.be/LF7fIXLJ-M4)

# GitHub Project Management Tools

In our project, we utilize various GitHub project management tools to streamline collaboration, track progress, and ensure efficient development practices to deliver high-quality results in a timely manner. These tools are essential for maintaining an organized workflow and facilitating effective communication within our team. Below are the key GitHub project management tools we have implemented:

## GitFlow Branching Strategy:

We adhere to the GitFlow branching strategy, which involves maintaining two main branches: main for final releases and develop for ongoing development. This approach allows us to integrate changes incrementally via pull requests (PRs) and ensures a structured workflow for feature development, bug fixes, and release management. We also allow hot-fix branches to merge changes directly into main when required.

## Branch Protection Rules:

We have configured branch protection rules for both the main and develop branches to enforce best practices and prevent direct changes. These rules require that all modifications to these branches must be made through PRs with approved reviews, promoting collaboration and ensuring code quality. For the repositories Kotlin and Flutter, we require 1 review from another team member for `develop` and 2 for `main`; for the repositories Wiki, Backend and Analytics, we require 2 reviews from other team members for `develop` and 4 for `main`.

## Squash and Merge:

Our repositories are configured to use the "squash and merge" option when merging PRs. This feature condenses multiple commits into a single, comprehensive commit, enhancing code readability and maintainability while preserving the project's commit history. Every PR merged must follow this convention.

## Pull Requests:

Pull Requests (PRs) are used extensively in our workflow to propose and review changes to the codebase. When a team member completes a task or implements a feature, they create a PR to merge their changes into the main codebase. PRs serve as a mechanism for peer review, allowing other team members to assess the proposed changes, provide feedback, and ensure code quality and consistency. Before merging, PRs must undergo thorough review and approval by at least one other team member. This collaborative process helps maintain code integrity, prevent errors, and foster knowledge sharing among team members. Additionally, PRs are linked to specific issues or tasks, providing traceability and context for the changes being made.

### Conversations

Conversations play a crucial role in our development process, facilitating discussions about implemented features, providing feedback, and ensuring clarity and understanding among team members. We encourage open communication and collaboration through various channels, including WhatsApp, GitHub discussions, and team meetings through Zoom. When features are implemented, team members engage in discussions to share insights, address potential issues, and brainstorm improvements. Feedback is actively solicited and welcomed, fostering a culture of continuous improvement and refinement. To enhance communication, we provide detailed descriptions of changes in pull requests, outlining the rationale behind each modification and highlighting key considerations. Whenever possible, we supplement these descriptions with demos, screenshots, or videos to provide visual context and aid comprehension. By encouraging discussions and providing comprehensive documentation, we ensure that all team members are informed and aligned, leading to more effective collaboration and higher-quality outcomes.


https://github.com/ISIS3510-202410-Team-13/Wiki/assets/68788933/3951b25d-2534-4870-9356-be5d26d1d881


### Reviews

Reviews are integral to our code review process, enabling team members to provide feedback, approve changes, and ensure code quality. We leverage GitHub's review tools extensively to conduct thorough and constructive code reviews. When reviewing pull requests, team members can comment on specific lines of code, pointing out potential issues, providing clarifications, or suggesting improvements. We encourage reviewers to request changes or seek clarification if something appears off, fostering a collaborative environment where concerns are addressed promptly and comprehensively. Once changes are made, reviewers can approve the pull request, indicating their confidence in the proposed modifications. Additionally, reviewers may suggest alternative approaches or offer guidance to help refine the code further. By actively engaging in reviews and leveraging GitHub's review tools, we uphold high standards of code quality and promote continuous learning and improvement within our team.


https://github.com/ISIS3510-202410-Team-13/Wiki/assets/68788933/c148debc-47fb-4405-8adb-84c134af7c0e

## Issues:

We created issues from planning sessions about the sprint workload and on-the-fly to register bugs and proposed improvements. We have defined the following general issue labels for classification:

- `bug`: Something isn't working
- `documentation`: Improvements or additions to documentation
- `feature`: Development of new features
- `GUI`: Graphical User Interface
- `tech-debt`: Reduce technical debt of the project
- `complementary-activities`: Non code for organizational, procedural, or administrative tasks

At the end of each sprint, we archive issues from previous sprints to keep our backlog board clean for future developments. Items from Sprint 1 can be found at the "Archived Items" section in GitHub Projects.

<img width="1728" alt="image" src="https://github.com/ISIS3510-202410-Team-13/Wiki/assets/68788933/0d5560db-1efa-49db-bbd5-c666263c414b">


## Issue Templates:

We have implemented issue templates to standardize the process of creating new issues, whether they are bug reports or feature requests. These templates guide users to provide essential details and follow a consistent format, facilitating clear communication and efficient issue triage. Every repository has 2 default templates: Bug Report and Feature Request. More templates are created based on need.

## Milestones:

We utilize milestones to mark significant points of progress within each sprint for every repository. Each milestone corresponds to a specific sprint duration, enabling us to effectively track and manage our progress towards achieving sprint goals and deliverables. By aligning milestones with sprint timelines, we ensure clear visibility into the project's advancement and enable team members to monitor their progress against predefined objectives. This milestone-based approach facilitates coordination and collaboration among team members, enhances accountability, and provides a structured framework for sprint planning and execution.


## Project Boards:

Our project boards are meticulously configured to optimize task management and progress tracking throughout our development lifecycle. Our project boards serve as a comprehensive tool for visualizing the development pipeline, organizing tasks effectively, and facilitating seamless collaboration among team members. With this structured approach, we ensure transparency, efficiency, and accountability in our project management processes. 

### Board Fields

Within the board, we have distinct fields representing several attributes of each planned task:

#### Status: Represents the current stage of each task within the development process.

- 📋 Backlog: Tasks in this column are meticulously planned and ready for execution.
- 📌 Ready: This column houses tasks that are prepared and awaiting commencement.
- 🏗️ In Progress: Tasks actively underway reside here, indicating active development efforts.
- 👀 In Review: Tasks that have been completed and are undergoing peer review are situated in this column.
- 🙌 Done: Tasks that have been successfully completed are archived in this column.

#### Priority: Indicates the importance or urgency level of each task.

- 🚨 High: Critical issues that require immediate attention and prompt delivery.
- 🤯 Medium: Important issues that need to be addressed promptly.
- ⛱️ Low: Relevant issues that can be postponed without significant impact.
- 🙌 Nice to have: Issues that are desirable but not crucial for immediate delivery.

#### Size: Reflects the estimated effort or complexity of each task.

- 🐣 Small: Issues that can be resolved within a few hours.
- 🐥 Medium: Issues that require attention and can typically be resolved within a day.
- 🐓 Large: Issues that demand more extensive effort and may take longer than a day to resolve.

#### Estimate:

Numerical values between 1 and 10 representing the estimated effort or complexity of each task.

#### Iteration:

Each iteration is aligned with the course syllabus and has defined start and end dates.

#### Start Date:

The designated start date for each task or iteration, ensuring clarity on when work should commence.

#### End Date:

The specified end date for each task or iteration, providing a deadline for completion to guide project scheduling and planning.

### Board Views

Board views are different perspectives or filters applied to the project board to visualize tasks and issues based on specific criteria or contexts. Each board view serves a unique purpose, allowing team members to focus on different aspects of the project, track progress, and make informed decisions. These views provide flexibility and customization options to adapt the project board to the needs of various stakeholders and project phases.

#### Current iteration:

This view displays all tasks and issues assigned to the current iteration, providing a focused perspective on the work planned for the ongoing sprint. It helps team members stay aligned with the sprint goals and track progress towards completing the planned deliverables within the specified timeframe.

<img width="1728" alt="image" src="https://github.com/ISIS3510-202410-Team-13/Wiki/assets/68788933/e9b8fbd8-b503-4d70-a1d6-60647044e1e4">

#### Team capacity:

This view shows the capacity of the team in terms of available resources and workload distribution. It allows team leads or project managers to visualize how the team's capacity aligns with the tasks assigned to them, helping to identify potential bottlenecks or overloads and enabling better resource allocation and planning.

<img width="1728" alt="image" src="https://github.com/ISIS3510-202410-Team-13/Wiki/assets/68788933/c47ddd55-10a7-417a-aafb-f47ff7b69c48">


#### Roadmap:

The Roadmap view provides a high-level overview of the project timeline and milestones. It outlines key deliverables, deadlines, and major milestones, helping stakeholders understand the project's progress and anticipated timeline for future releases or iterations. This view aids in long-term planning and strategic decision-making.

<img width="1728" alt="image" src="https://github.com/ISIS3510-202410-Team-13/Wiki/assets/68788933/c5ff8c3d-0ba8-4e69-bff9-c42ba5306b13">

#### My items:

This view filters and displays tasks and issues assigned to the logged-in user. It provides a personalized perspective, allowing individuals to focus on their own responsibilities and track the status of tasks assigned to them. This view enhances individual productivity and accountability by highlighting tasks relevant to each team member.

<img width="1728" alt="image" src="https://github.com/ISIS3510-202410-Team-13/Wiki/assets/68788933/56ee3152-ea5d-44d5-8048-39fb1960cb99">

#### Backlog:

The Backlog view contains all tasks and issues that have been identified but are not yet scheduled for implementation. It serves as a repository for ideas, feature requests, and other potential work items, allowing the team to prioritize and plan future iterations or releases based on business needs and stakeholder feedback.

<img width="1728" alt="image" src="https://github.com/ISIS3510-202410-Team-13/Wiki/assets/68788933/41978c5b-5c1f-48c0-a9f1-be249bf036f8">

## Automated Workflow Rules:

In our project, we have implemented several automated workflow rules to enhance task management efficiency and facilitate seamless status updates. These automated workflows help streamline the progression of tasks through different stages of development, ensuring clear visibility and accountability. Below are the default workflows we have configured:

1. Item Added to Project:
When a new item, such as an issue or feature request, is added to the project, it is automatically assigned to the appropriate project board and column based on predefined criteria. This ensures that tasks are immediately visible and actionable within the project management system.

2. Item Reopened:
If an item, such as an issue or pull request, is reopened after being closed, it is automatically reactivated and moved to the relevant column in the project board. This allows for easy tracking of reopened tasks and ensures that they are promptly addressed.

3. Item Closed:
When an item, such as an issue or pull request, is closed after completion or resolution, it is automatically archived or moved to a designated "Closed" column in the project board. This helps maintain a clean and organized project board by removing completed tasks from the active workflow.

4. Code Changes Requested:
When feedback or changes are requested on a pull request, the associated issue is automatically transitioned back to the "In Progress" column in the project board. This indicates that additional work is required before the pull request can be merged, facilitating efficient collaboration and follow-up.

5. Code Review Approved:
Upon approval of a pull request during the code review process, the associated issue is automatically moved to the "In Review" column in the project board. This signifies that the code changes have been reviewed and approved, and the task is ready for final validation and merging.

6. Pull Request Merged:
When a pull request is successfully merged into the main branch, the associated issue is automatically closed or moved to the "Done" column in the project board. This reflects the completion of the task and ensures that it is properly archived or marked as completed within the project management system.

7. Auto-Archive Items:
Items that have been closed or completed are automatically archived or moved to a designated "Archived" column in the project board after a specified period of inactivity. This helps declutter the project board and keeps it focused on active tasks and priorities.

8. Auto-Add to Project:
When a new item, such as an issue or pull request, is created, it is automatically added to the relevant project board and column based on predefined criteria. This ensures that all tasks are consistently tracked and managed within the project management system from inception to completion.

By implementing these automated workflow rules, we optimize our project management process, promote collaboration among team members, and maintain transparency and accountability throughout the development lifecycle.

# Sprint 2 Contributions

Our teammate _Lucciano Franco_ decided to withdraw from the course on Thursday 21 of March at night.

- ## Laura Daniela Arias Flórez
  - Design and Creation of UI
    - Add Friend
    - Add Friend Confirmation
    - Add Friend Finished
  - Proposed Solution
  - Implementation of Business Question 3.4
  - Design of Analytics Pipeline
  - GUI Implementation: Home Kotlin
  - Feature Implementation: Biometrical Authentication + Meeting Place Recommendation + User Feedback (Kotlin)
- ## Juan Diego Castellanos Bonilla
  - Design and Creation of UI
    - Friend Chat
    - Group Chat
  - Revenue Model
  - Implementation of Business Question 2.3
  - Design of Analytics Pipeline
  - GUI Implementation: Calendar Kotlin
  - Feature Implementation: Event Notification (Kotlin) + Meeting Place Recommendation + User Feedback (Kotlin)
- ## Juan Sebastián Urrea López
  - Design and Creation of UI
    - Home-Group
    - Calendar Group
  - Configuration of Gitflow
  - Implementation of Business Question 5.2
  - Architectural Design: Context Diagram and Backend Components
  - GUI Implementation: Add Event Flutter
  - Feature Implementation: Meeting Place Recommendation + User Feedback (Flutter)
- ## Juan Esteban Cuellar Argotty
  - Definition of UI/UX: Color Palette, Fonts, Icons and Images
  - Design and Creation of UI
    - Calendar
    - Hamburger Menu
    - Profile
    - Friends
  - Implementation of Business Question 2.1
  - Architectural Design: Domain Driven and Class Diagram
  - GUI Implementation: Calendar Flutter
  - Feature Implementation: Biometrical Authentication + Event Notification + User Feedback (Flutter)
- ## David Santiago Ortiz Almanza
  - Definition of Value Proposition
  - Design and Creation of UI
    - Loading Screen Animation
    - Home
    - Notifications
    - Add/Edit Class
    - Groups
  - Implementation of Business Question 4.1
  - Architectural Design: Deployment Diagram
  - GUI Implementation: Home Flutter
  - Feature Implementation: Biometrical Authentication + Event Notification + User Feedback (Flutter)

