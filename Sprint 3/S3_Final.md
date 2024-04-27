# Table of Contents

1. [Eventual Connectivity Scenarios](#eventual-connectivity-scenarios)
   - [Scenario 1: Offline Authentication Failure](#scenario-1-offline-authentication-failure)
   - [Scenario 2: Friends/Groups/Events Offline Access](#scenario-2-friendsgroups-events-offline-access)
     - [Friends](#friends)
     - [Groups](#groups)
     - [Events](#events)
   - [Scenario 3: Available Spaces Query](#scenario-3-available-spaces-query)
   - [Scenario 4: Offline Events Creation](#scenario-4-offline-events-creation)
   - [Scenario 5: Internet Connection Down](#scenario-5-internet-connection-down)
2. [Functionalities and design details implemented for Sprint 3.](#functionalities-and-design-details-implemented-for-sprint-3)
   - [List of Features](#list-of-features)
     - [Sprint 2](#sprint-2)
     - [Sprint 3](#sprint-3)
   - [Business Questions](#business-questions)
     - [BQ 1.1](#bq-11)
     - [BQ 1.2](#bq-12)
     - [BQ 2.2](#bq-22)
     - [BQ 3.3](#bq-33)
     - [BQ 4.2](#bq-42)
   - [Implemented Eventual Connectivity Strategies](#implemented-eventual-connectivity-strategies)
   - [Implemented Local Storage Strategies](#implemented-local-storage-strategies)
   - [Implemented Multi-Threading Strategy](#implemented-multi-threading-strategy)
   - [Implemented Caching Strategies](#implemented-caching-strategies)
6. [Ethics Video](#ethics-video)
7. [Sprint 3 Contributions](#sprint-3-contributions)


# Eventual Connectivity Scenarios
## Scenario 1: Offline Authentication Failure

  _Designed by: Juan Sebastian Urrea Lopez_

  - **ID:** 1
  
  - **Event description:** The user is filling the signup or login forms. Their credentials are sent, but the petition fails because connectivity is lost.

  - **System response:** Cancel the authentication process and inform the user that they need internet connection to login or signup with clear error messages.

  - **Possible Anti-patterns:** #3 Non-Informative Message, #7 Unavailable functionality after connection recovery.

  - **Caching and retrieving strategy:** Network Only.

  - **Storage type:** Cache Manager.

  - **Stored data type:** Single value for the email typed in the form. The password should never be saved.

  - **Additional notes:** If the user has already logged in before, we do not request credentials again. Instead, we use biometric authentication to allow them to use the app. For this reason, internet connection is not required for this case.

## Scenario 2: Friends Offline Access

_Designed by: Juan Diego Castellanos Bonilla_

  - **ID:** 2

  - **Event description:** The user  is going to see his friends. It sends a petition to load the friends, but as the conection is lost the friends won´t load.

  - **System response:** load the friends that where saved on the local storage.  

  - **Possible Anti-patterns:** #3 Non-Informative Message. #5 Non-existent Result Notification.

  - **Caching and retrieving strategy:** Network falling back to cache

  - **Storage type:** local Data Manager.

  - **Stored data type:** Single value for the Name of the friend.


## Scenario 3: Groups Offline Access

_Designed by: Juan Diego Castellanos Bonilla_

  - **ID:** 3

  - **Event description:** The user  is going to see his groups. It sends a petition to load the groups, but as the conection is lost the groups won´t load.

  - **System response:** load the groups that where saved on the local storage.

  - **Possible Anti-patterns:** #3 Non-Informative Message. #5 Non-existent Result Notification.

  - **Caching and retrieving strategy:** Network falling back to cache

  - **Storage type:** local Data Manager and cache (for images).

  - **Stored data type:** Single value for the color of the group. Single or multiple events of the group (depends on case). Single url of group picture. Single icon. Multiple members of the group


## Scenario 4: Events Offline Access

_Designed by: Juan Diego Castellanos Bonilla_

  - **ID:** 4

  - **Event description:** The user is going to see his events. It sends a petition to load the events he have, but there is not answer from server as the connection is lost.  

  - **System response:** Load the event from the cache and inform the user the reason why the event may not be up to date, but as soon as the connection is back it synchronize the data.

  - **Possible Anti-patterns:** #3 Non-Informative Message. #5 Non-existent Result Notification.

  - **Caching and retrieving strategy:** save events information when app is launch and retrieving from the local Data, when connection is recovered, sync with online data to check if the information was changed.

  - **Storage type:** Cache then network

  - **Stored data type:**  Single value for the color of the event. Single value for the description of the event. Single value for the start date of the event. Single value for the end date of the event. Multiple values for labels. Single value for the name of the event. Single value for the time of reminder of the event.

## Scenario 5: Available Spaces Query
  _Designed by: Laura Daniela Arias Flórez_

  - **ID:** 5
  
  - **Event description:** The user is creating a new event and knows thy can request available spaces suggestions, however, they lose internet connection.

  - **System response:** The space suggestion button is disabled, and the user is informed through the app’s screen that internet is needed do make use of that space suggestion feature.

  - **Possible Anti-patterns:** #3 Non-informative message, #8 Unclear behavior

  - **Caching and retrieving strategy:** N/A

  - **Storage type:** N/A

  - **Stored data type:** N/A


## Scenario 6: Offline Events Creation
  _Designed by: David Santiago Ortiz Almanza_

  - **ID:** 6
  
  - **Event description:** The user creates an important event that must remember in its calendar however its in a place without internet connection.

  - **System response:** The event is saved locally and shown within the application. Once the internet connection is restored, the application checks locally for events that require synchronization and attempts to synchronize each one with the server.

  - **Possible Anti-patterns:** #4 Lost Content, #9 Unexpected Result from Background Process.

  - **Caching and retrieving strategy:** Generic Fallback.

  - **Storage type:** Hive.

  - **Stored data type:** Key Value Pair (<string, Event>)


## Scenario 7: Internet Connection Down
 _Designed by: Juan Esteban Cuellar Argotty_

  - **ID:** 7
  
  - **Event description:** The user is interacting with the UniSchedule application, and suddenly the internet goes down.

  - **System response:** When the user's device is connected to the internet, a WiFi icon is displayed in the AppBar. If the device loses internet connectivity, a WiFi-off icon is shown instead to indicate the disconnected status.

  - **Possible Anti-patterns:** #3 Non-informative message, #8 Unclear behavior

  - **Caching and retrieving strategy:** Not applicable

  - **Storage type:** Not applicable

  - **Stored data type:** Not applicable

# Functionalities and design details implemented for Sprint 3.

## List of Features
> *You might find text in Spanish in the following demos. Worry not! We fixed it for the Sprint Release.*
### Sprint 2
1. **Biometrical Authentication**

This functionality utilizes at least one sensor in the phone, such as fingerprint or facial recognition technology, to authenticate users. Biometric authentication offers a secure and convenient way for users to access the application without the need for traditional password-based authentication.

**Related:** [Flutter#22](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/22) - [Kotlin#10](https://github.com/ISIS3510-202410-Team-13/Kotlin/pull/10)

https://github.com/ISIS3510-202410-Team-13/Wiki/assets/68788933/1682bc3b-ebc0-437f-9034-4a16484f0ee6

2. **Event Notification**

This functionality provides users with notifications about upcoming events or important updates within the application. Users receive timely alerts and reminders, ensuring they stay informed about their schedules and any relevant changes or additions.

**Related:** [Flutter#32](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/32) - [Flutter#29](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/29) - [Kotlin#14](https://github.com/ISIS3510-202410-Team-13/Kotlin/pull/14)

https://github.com/ISIS3510-202410-Team-13/Wiki/assets/68788933/108ae367-b448-4c01-8d5d-cc52cb8fa1cb


3. **Meeting Place Recommendation**

This functionality utilizes the AvailableSpaces service provided by our backend to recommend suitable meeting places based on user preferences and availability. The AvailableSpaces service retrieves information about available spaces within specified time frames and days of the week at the campus of Universidad de los Andes. By integrating our mobile frontend with this external data source, our application can leverage smart algorithms to generate personalized recommendations that optimize convenience and accessibility for user meetings. The service implementation and detailed documentation is available at the [Backend Services](https://github.com/ISIS3510-202410-Team-13/Backend) repository.


**Related:** [Flutter#34](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/34) - [Flutter#26](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/26) - [Backend#2](https://github.com/ISIS3510-202410-Team-13/Backend/pull/2)

https://github.com/ISIS3510-202410-Team-13/Wiki/assets/68788933/b256b583-d4bf-4137-b5c1-8fc6e7f828d4

4. **User Feedback**

This functionality allows users to provide feedback on a crucial aspect of the application: the available spaces recommendation system. User feedback is essential for continuous improvement, helping the development team identify areas for enhancement and prioritize future updates to enhance the user experience.

**Related:** [Flutter#36](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/36)

https://github.com/ISIS3510-202410-Team-13/Wiki/assets/68788933/7e9d607a-3311-474b-855a-cd9de51a81e1

### Sprint 3

1. **Connectivity status**

This feature checks and displays the internet connection status of the device. Users can see whether they are connected to the internet . This is particularly useful in a mobile application where connectivity may frequently change due to location or network shifts.

**Related:** [Flutter#121](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/121) 

https://github.com/ISIS3510-202410-Team-13/Flutter/assets/78111224/da1154ba-67cb-4a2f-8059-30b0fd8b2bdf



2. **Functional Search Bars**

This feature implements functional search bars across friends and groups sections of the application, allowing users to perform quick and efficient searches. These search bars are capable of filtering results in real-time based on the entered text, improving the navigation and accessibility of information.

**Related:** [Flutter#82](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/82) 

https://github.com/ISIS3510-202410-Team-13/Flutter/assets/78111224/f2b92da5-f3dd-4340-b58c-4f48d7a90b56



3. **User sign-up and sign-in w/ credentials**

This functionality allows users to sign up and log in using credentials such as email and password. This ensures that access to the application is secure and user information remains private and safe. Additionally, it facilitates the customization and storage of user data.

**Related:** [Flutter#103](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/103) 


https://github.com/ISIS3510-202410-Team-13/Flutter/assets/68788933/23a68ba6-7425-416d-83cd-893fde82db9a


https://github.com/ISIS3510-202410-Team-13/Flutter/assets/68788933/2e1fae5b-775d-4e99-9cab-6fa1694082e5




4. **Create/renderize personal events**

This functionality enables users to create personal events that can be visualized on the calendar [age.Users can manage their events by setting details such as date, time, and description, making it easier to organize their activities and commitments.


**Related:** [Flutter#97](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/97) -  [Flutter#106](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/106) 


https://github.com/ISIS3510-202410-Team-13/Flutter/assets/78111224/5c9c736f-f905-42ea-a707-3d7d3f8c7a41



## Business Questions

Previously, we tackled BQ 2.1, 2.3, 3.4, 4.1 and 5.2 (see [Sprint 2](https://github.com/ISIS3510-202410-Team-13/Wiki/wiki/S2_Final)). In this Sprint, we are implementing the following:

### BQ 1.1

_Developed by: Juan Esteban Cuellar Argotty_

**Question:** What are the most common devices and operating systems experiencing crashes within the UniSchedule app, and are there specific features associated with these crashes?

**Justification:** This question is categorized under App's Telemetry because it directly addresses app stability issues (crashes) and seeks to correlate them with specific types of devices and operating systems, which is essential for identifying and rectifying compatibility or performance-related problems.

### BQ 1.2

_Developed by: David Santiago Ortiz Almanza_

**Question:** What are the most reported bugs within UniSchedule's latest version, and how do these impact app functionalities?

**Justification:** This question is categorized under App's Telemetry because it directly addresses app stability issues (crashes) and seeks to correlate them with specific types of devices and operating systems, which is essential for identifying and rectifying compatibility or performance-related problems.

### BQ 2.2

_Developed by: Juan Sebastian Urrea Lopez_


  **Question:** How effectively does the app's automatic suggestion feature for available spaces on campus enhance users' ability to find suitable locations for their events?

  **Justification:** This question focuses specifically on evaluating the effectiveness of one key feature of the app: the automatic suggestion of available spaces on campus for events. By honing in on this aspect, we can assess users' experiences with finding and selecting suitable locations for their activities. Insights from this question can inform refinements to the suggestion algorithm and user interface, ensuring that users can easily discover and book appropriate spaces for their events, ultimately enhancing their overall experience with the app.

### BQ 3.3
_Developed by: Juan Diego Castellanos Bonilla_


**Question:** Which functionalities within competitor apps are most utilized by our target demographic, and how do these compare with the current feature set of UniSchedule?

**Justification:** This question compares UniSchedule's features against those of competitors, focusing on user engagement and preferences. The analysis is aimed at identifying gaps in the app's feature set or opportunities for innovation, directly informing the development or refinement of features to better meet user needs.

### BQ 4.2
_Developed by: Laura Daniela Arias Flórez_

**Question:** What is the average weekly usage time per user within UniSchedule, and which specific section of the app engages users the longest for placing advertisements?

**Justification:** This question is classified as Type 4 because it focuses on understanding user engagement metrics within the app, such as average usage time and most visited sections, with the aim of leveraging this data for monetization purposes. By identifying the sections of the app where users are most active, the business can optimize advertisement placements to ensure maximum visibility and engagement, thereby enhancing the value proposition for potential advertisers.

## Implemented Eventual Connectivity Strategies


Our eventual connectivity strategy includes several key components to ensure a seamless user experience, even in offline scenarios:

* Event creation can be performed without an internet connection. Once connectivity is restored, any events created offline are automatically synchronized.

* In the absence of an internet connection, local storage data for Groups, Friends, and Events is displayed, allowing users to have an online-like experience.

* An icon within the app indicates whether the mode is online or offline. Additionally, a modal appears when connectivity changes, informing the user of the status change.

* For user registration and initial login, if there is no internet connection, a clear message is displayed to the user indicating that an internet connection is required to proceed. After the initial login, internet is not necessary for authentication and users can log in using their fingerprint.

* The feature that recommends places for meetings disables and alters the appearance of the corresponding button when no internet is detected, clearly communicating that a connection is required to use this feature.

* If there is no internet connection and local storage does not contain any Groups, Friends, or Events data, the user is informed that the information could not be loaded and that an internet connection is required.


## Implemented Local Storage Strategies

In our application, implementing local storage strategies is crucial for enhancing offline functionality and providing a seamless user experience, even in the absence of an internet connection. Here’s a detailed breakdown of our local storage implementation:

- **Objective:** The primary goal of storing user groups, friends, and events locally is to ensure that users can access these crucial features even when offline. This functionality is especially important for maintaining usability during network disruptions.


#### **Advantages of This Approach:**
1. **Enhanced Performance:** Accessing data from local storage is significantly faster than fetching it over the internet, leading to quicker load times and a smoother user experience.
2. **Reliability:** Users can rely on the app to function effectively even when they are offline, which is crucial for mobile applications where constant connectivity cannot be guaranteed.
3. **Data Integrity:** By syncing data whenever the internet connection is available, we ensure that the user's information remains up-to-date across all devices.



**Related:** [Flutter#88](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/88) - [Flutter#104](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/104) - [Flutter#105](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/105)


https://github.com/ISIS3510-202410-Team-13/Wiki/assets/78111224/75e75f9c-0459-4a17-8734-f21a04931617



## Implemented Multi-Threading Strategy

Our multi-threading strategy involves using an asynchronous thread for each API call at the application's start (one for Friends, another for Groups, and another for Events). This approach is adopted because retrieving this information is slow, and we aim to avoid blocking the main thread (GUI). Additionally, by initiating these calls at the application's launch, we ensure that the information is ready when the user needs to access these views.

**Related:** [Flutter#80](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/80) 

## Implemented Caching Strategies

The caching strategy we implemented involves storing user images (displayed in both the Friends and Groups views) in a cache at reduced quality for two main purposes: 1. To enhance application performance: Since user images are cloud-based, they needed to be rendered continuously, but caching them accelerates this process significantly. 2. To provide eventual connectivity support, allowing users to access the Friends and Groups views even when there is no internet connection.

**Related:** [Flutter#90](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/90) 

https://github.com/ISIS3510-202410-Team-13/Flutter/assets/69651671/6cf5a051-091d-4665-8859-de29b0672e4b

# Ethics Video

https://youtu.be/LqS2TXsGTA8

# Sprint 3 Contributions

## Flutter Team


### Juan Esteban Cuellar Argotty

#### User Interface Development and Usability Improvements
- **Interface components improvements:** Created and styled the slide-out menu, implemented friend views, managed empty states for groups and events, and added a connectivity status icon. Also refined the search bar functionality and the floating action button (PR #84, #55, #111, #121, #120, #61).

#### Event and Calendar Features
- **Personal and calendar event management:** Added event handling with functionality for creating personal events and dynamic data rendering in existing views (PR #106, #86, #78).

#### Optimization and Bug Fixes
- **Bug fixes and enhancements:** Solved persistent filtering issues in friend and group navigation (PR #96).

### Juan Sebastián Urrea López

#### Authentication and Security
- **Authentication implementation and improvement:** Enhanced the authentication process and field validation. Also added error handling in request building for available spaces and in authentication (PR #103, #124, #126, #123).

#### Optimizations and Bug Corrections
- **General corrections and performance improvements:** Fixed errors in scheduled notifications, group profile rendering issues, and event value calculations in the calendar view (PR #125, #109, #108).

#### Refactoring and Documentation
- **Architecture refinement and documentation:** Refactored the calendar view into multiple widgets and documented the architectural changes (PR #95, #99).

### David Santiago Ortiz Almanza

#### Multithreading Features and Local Storage
- **Multithreading and local storage implementation:** Developed multithreading functionality for API calls for friends and groups and managed local storage for events, friends, and groups (PR #80, #88, #105).

#### User Interface and User Experience
- **Group and event interface development:** Implemented the initial groups page and managed network image cache strategies for profile icons (PR #51, #90).

#### Error Corrections and Usability Enhancements
- **Functionality and display error correction:** Fixed an error that failed to display text when there were more elements and disabled meeting place recommendations without an internet connection. Also implemented a calendar page and corrected errors allowing events to start and end on different days without proper rendering (PR #112, #114, #107, #122).



## Kotlin Team
- ### Laura Daniela Arias Flórez

  ####  Bug Fixes
  - **Bug fixes:** Solved persistent filtering issues in friend and group  (PR# 37).

  #### Group sview
  - **Group screen implementation:** Developed Group screen (PR # 37).

  #### Eventual Connectivity
  - **Eventual connectivity implementation:** Developed local storage management for Events (PR #46).

  #### Add Event view
  - **Add Event SCREEN implementation:** Developed Add Event screen (PR # 50).

- ### Juan Diego Castellanos Bonilla

  #### Local Storage
  - **Local storage implementation:** Developed managed local storage for events, friends, and groups (PR #40, #45, #39).

  #### Eventual connectivity
  - **Eventual connectivity implementation:** Developed the states and code to see eventual connectivity for the app (PR #41).

  #### View of friends 
  - **Friend view implementation:** Developed friend view with searchBar (PR #43).

  #### Eventual connectivity offline
  - **Eventual connectivity offline implementation:** Developed managed local storage for groups, friends (PR #44, #45, #39).
