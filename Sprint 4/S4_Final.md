# Table of Contents

1. [UniSchedule Value Proposition](#unischedule-value-proposition)
    - [Problem Addressed](#problem-addressed)
    - [Simplifying Complex Schedule Coordination](#simplifying-complex-schedule-coordination)
    - [Enhancing Productivity and Time Management](#enhancing-productivity-and-time-management)
    - [Ensuring Security and Privacy](#ensuring-security-and-privacy)
    - [Providing Reliable Offline Functionality](#providing-reliable-offline-functionality)
    - [Enabling Continuous Improvement through Feedback](#enabling-continuous-improvement-through-feedback)
    - [Generating Sustainable Revenue](#generating-sustainable-revenue)
    - [Delivering Personalized Recommendations](#delivering-personalized-recommendations)
    - [Ensuring Clear Communication and User Awareness](#ensuring-clear-communication-and-user-awareness)
    - [The App you were waiting for!](#the-app-you-were-waiting-for)

2. [Micro-Optimization Strategies](#micro-optimization-strategies)
    - [GPU Rendering Analysis](#gpu-rendering-analysis)
        - [Login Process](#login-process)
        - [Event Creation and Recommendation Tool](#event-creation-and-recommendation-tool)
        - [Filtering Friends and Groups](#filtering-friends-and-groups)
        - [Oversized Images Analysis](#oversized-images-analysis)
    - [Overdrawing Analysis](#overdrawing-analysis)
    - [Memory Management Analysis](#memory-management-analysis)
        - [Login Process](#login-process-1)
        - [Event Creation and Recommendation Tool](#event-creation-and-recommendation-tool-1)
        - [Filtering Friends and Groups](#filtering-friends-and-groups-1)

3. [Features Delivered](#features-delivered)
    - [Sprint 2](#sprint-2)
    - [Sprint 3](#sprint-3)
    - [Sprint 4](#sprint-4)

4. [Business Questions (BQs)](#business-questions-bqs)
    - [Type 1: Crashlytics and Telemetry](#type-1-crashlytics-and-telemetry)
    - [Type 2: User Experience](#type-2-user-experience)
    - [Type 3: Feature Usage](#type-3-feature-usage)
    - [Type 4: Monetization](#type-4-monetization)
    - [Type 5: Cross-category](#type-5-cross-category)

5. [Implemented Eventual Connectivity Strategies](#implemented-eventual-connectivity-strategies)
6. [Implemented Local Storage Strategies](#implemented-local-storage-strategies)
7. [Implemented Multithreading Strategies](#implemented-multithreading-strategies)
8. [Implemented Caching Strategies](#implemented-caching-strategies)
9. [Ethics Video](#ethics-video)
10. [Sprint 4 Contributions](#sprint-4-contributions)
    - [David Santiago Ortiz](#david-santiago-ortiz)
    - [Juan Esteban Cuéllar](#juan-esteban-cu%C3%A9llar)
    - [Juan Sebastian Urrea](#juan-sebastian-urrea)


# UniSchedule Value Proposition

## Problem Addressed

UniSchedule tackles the complex and often stressful task of schedule coordination for university students. Traditional methods of managing schedules and arranging meetings are time-consuming and inefficient, particularly when juggling multiple commitments and platforms. Additionally, privacy and data security concerns complicate the management of personal information and schedules. UniSchedule aims to provide a unified, secure, and efficient solution to streamline time management and enhance collaboration without compromising user privacy.

## Simplifying Complex Schedule Coordination

UniSchedule addresses the inherent complexity and inconvenience faced by university students in managing their schedules and coordinating meetings. By integrating diverse functionalities into a single, user-friendly platform, UniSchedule simplifies the process of finding common availability and setting up meetings, thereby saving users significant time and effort. The app's design ensures that it can operate seamlessly even during connectivity issues, enhancing reliability and user trust.

## Enhancing Productivity and Time Management

UniSchedule significantly boosts productivity by providing timely notifications and smart recommendations. Users can stay organized, prioritize tasks effectively, and avoid missing important events, all of which contribute to a more productive and stress-free daily routine. The ability to create and manage events offline ensures that users are not hindered by connectivity problems, allowing them to maintain control over their schedules at all times.

## Ensuring Security and Privacy

The app prioritizes user security and privacy through robust authentication mechanisms, including biometric authentication. This reassures users that their personal data and schedule information are safe, fostering trust in the application. Secure access controls further ensure that user information remains private, addressing a major concern for users who are increasingly aware of data privacy issues.

## Providing Reliable Offline Functionality

UniSchedule's ability to function effectively offline by utilizing local storage ensures that users have access to crucial information even without an internet connection. This reliability is particularly valuable for students who may frequently move between different network environments. The app's offline capabilities mean users can rely on UniSchedule for uninterrupted access to their schedules and important data, enhancing its utility and user satisfaction.

## Enabling Continuous Improvement through Feedback

The integration of user feedback mechanisms allows UniSchedule to continuously evolve based on user input. This commitment to improvement ensures that the app remains relevant and meets the evolving needs of its users. By actively seeking and incorporating feedback, UniSchedule can refine its features and enhance the overall user experience, leading to higher user satisfaction and retention.

## Generating Sustainable Revenue

UniSchedule employs a balanced approach to revenue generation through in-app advertising and data monetization. Non-intrusive banner ads provide a steady revenue stream without significantly disrupting the user experience. Additionally, offering a paid, ad-free version caters to users who prefer an uninterrupted experience. Data monetization leverages anonymized user data to provide valuable insights to third parties, creating additional revenue opportunities while maintaining user privacy.

## Delivering Personalized Recommendations

By leveraging smart algorithms and data from the AvailableSpaces service, UniSchedule offers personalized meeting place recommendations. This feature enhances the user experience by providing convenient and relevant suggestions, making the process of organizing meetings more efficient and tailored to user preferences.

## Ensuring Clear Communication and User Awareness

UniSchedule enhances user experience by providing clear communication about connectivity status and feature availability. Real-time indicators and notifications keep users informed about their internet connection status and any impact on app functionality, preventing confusion and ensuring transparency.

## The App you were waiting for!

UniSchedule's value proposition lies in its ability to simplify schedule management, enhance productivity, ensure security, provide reliable offline functionality, continuously improve through feedback, generate sustainable revenue, deliver personalized recommendations, and maintain clear communication. By addressing the key pain points of university students and offering a comprehensive, reliable, and user-friendly solution, UniSchedule positions itself as an essential tool for effective time management and coordination. This holistic approach not only meets the immediate needs of users but also fosters long-term engagement and trust in the app.

# Micro-Optimization Strategies

## GPU Rendering Analysis

https://github.com/ISIS3510-202410-Team-13/Wiki/assets/78111224/f4e8861f-37ad-4c89-ba34-8c011212303f

### Login Process

During the initial login process, a notable increase in frame time was observed, particularly in the UI thread. This surge is attributed to the heavy computations and data loading necessary for authentication and setting up the user environment. The UI thread experienced significant activity as it processed the login credentials and initialized the user's session. Despite the initial spike, the system demonstrated efficient handling of these tasks, stabilizing quickly. This indicates that while the login process is resource-intensive, the current implementation manages it effectively without prolonged performance degradation.

### Event Creation and Recommendation Tool

When creating events, another significant rise in frame time was recorded. The increased activity in the UI thread during this period is aligned with the complexity of rendering new event forms and updating the calendar view. The recommendation tool for places also caused noticeable spikes in frame time. This tool performs intensive computations to filter and suggest suitable locations, resulting in temporary performance hits. These spikes, although momentary, highlight the computational demands of the recommendation algorithm and suggest that optimization in this area could lead to a smoother user experience.

### Filtering Friends and Groups

The actions of filtering friends and groups showed increased frame times and occasional jank, indicating that these operations are adding substantial load to the system. The analysis revealed that this was further exacerbated by oversized images in the home and calendar tabs, which significantly added to the rendering load. These oversized images caused additional strain on the UI thread, leading to frame drops and an overall decrease in responsiveness. Optimizing image sizes and implementing better image loading strategies could mitigate these issues and improve the performance during filtering operations.


The performance analysis identified key areas where the application can be optimized to enhance user experience. The initial login process, while resource-intensive, stabilizes quickly and efficiently. However, event creation and the recommendation tool for places present opportunities for optimization due to their high computational demands. Additionally, filtering friends and groups, combined with the presence of oversized images, further impacts performance. Addressing these issues through optimization strategies will result in a more responsive and user-friendly application. Implementing these changes will not only improve performance but also increase user satisfaction and engagement.

### Oversized Images Analysis

<img src="https://github.com/ISIS3510-202410-Team-13/Wiki/assets/78111224/c3184f57-3d05-4400-89e0-54afd8fe23ae" width="325">
<img src="https://github.com/ISIS3510-202410-Team-13/Wiki/assets/78111224/e935beb8-6c52-48e4-adfe-4a5597aab4f2" width="325">

We observe issues with GPU rendering upon entering the calendar and home section. Specifically, the most significant problem occurs when attempting to render the main image of the view. Upon entering the detail and using the profiling tool that highlights and flips images occupying substantial space, we can see that this main image is indeed causing the issue. This could be resolved by reducing the resolution of the image, as its size ensures that the reduction in quality will not be noticeable. This adjustment would decrease the load on the GPU and enhance the overall performance.

## Overdrawing Analysis

https://github.com/ISIS3510-202410-Team-13/Wiki/assets/69651671/e7fffceb-481b-456f-91c1-ebc92a986601


In the "UniSchedule" app, it was observed that there is no overdraw as the Android debug tool paints everything blue, except during interactions external to the application such as when the keyboard is deployed for typing.

Regarding repainting, generally, the app does not exhibit excessive repainting. However, in sections where text fields are written into or when the date and time of an event are changed, some repainting of those sections occurs. The most significant problem was detected during the creation of events when adding participants and labels, as it caused repainting of a large portion of the event creation form.

This minimal overdraw indicates efficient UI layering and resource usage, a positive aspect for the "UniSchedule" app. On the other hand, the repainting observed in specific interactions could impact user experience and performance. The excessive repainting during event creation suggests potential inefficiencies in how state changes are managed within the form. Optimizing these interactions could improve the overall performance and responsiveness of the application.

## Memory Management Analysis


https://github.com/ISIS3510-202410-Team-13/Wiki/assets/78111224/a277cdf8-7f85-4270-bda2-e681afb7c497


### Login Process

During the initial login process, a significant number of instances were created, particularly for classes related to UI rendering and data handling. Notably, the `Frame` and `_Node` classes exhibited high instance counts and memory usage, which is expected due to the intensive operations required for setting up the user interface and loading user data. Despite the temporary increase in memory usage, these instances were effectively managed, with a substantial portion allocated in the new space, indicating efficient garbage collection. However, there were isolated instances of memory leaks associated with the `Frame` class that need addressing to prevent long-term performance degradation.

### Event Creation and Recommendation Tool

Creating events and using the recommendation tool for places also resulted in notable memory usage spikes. Classes such as `_$GroupModel` and `_$FriendModel`, which are involved in managing event data and recommendations, showed increased instances and memory allocation. The memory data indicates that these objects are predominantly allocated in the new space, with minimal promotion to the old space, suggesting efficient short-term memory usage. Nevertheless, the high instance counts and sizes highlight potential areas for optimization. For example, refactoring these classes to reduce object creation overhead or employing object pooling techniques could significantly enhance memory efficiency.

### Filtering Friends and Groups

Filtering friends and groups revealed increased memory allocation, particularly for classes handling UI components and data models. The `EqualUnmodifiableListView` class showed a significant number of instances, reflecting the demand for managing filtered lists. Additionally, memory fragmentation issues were detected, leading to increased garbage collection overhead. To mitigate this, implementing more efficient data structures and algorithms for filtering operations is recommended. This will not only reduce memory usage but also enhance the application's responsiveness during intensive filtering tasks.


![image](https://github.com/ISIS3510-202410-Team-13/Wiki/assets/78111224/c99a095c-be25-4881-a8a6-d499358eb6c6)

Overall, the memory management analysis identified key areas for optimization to improve the application's performance and stability. While the initial login process and short-term memory usage during event creation and recommendations are managed efficiently, there are opportunities to optimize object creation and reuse. Addressing memory leaks, optimizing data structures for filtering operations, and reducing memory fragmentation will further enhance the application's responsiveness and user experience. Implementing these optimizations will lead to better memory management, reduced latency, and increased user satisfaction.

# Features Delivered

## Sprint 2

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


## Sprint 3

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


4. **Create/render personal events**

This functionality enables users to create personal events that can be visualized on the calendar [age.Users can manage their events by setting details such as date, time, and description, making it easier to organize their activities and commitments.


**Related:** [Flutter#97](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/97) -  [Flutter#106](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/106) 


https://github.com/ISIS3510-202410-Team-13/Flutter/assets/78111224/5c9c736f-f905-42ea-a707-3d7d3f8c7a41


## Sprint 4

1. **Group Creation**

This functionality allows users to create groups by specifying details such as the group name, members, and a representative color. This makes it easier to organize activities and commitments, as users can effectively visualize and manage their groups on the calendar.

**Related:** [Flutter#148](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/148) - [Flutter#134](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/134)

https://github.com/ISIS3510-202410-Team-13/Flutter/assets/69651671/7ae3d425-a2ed-47f3-ae5d-1c6d9fedae1a

2. **Notification broadcasting** 

This functionality enables users to receive notifications about external events such as updates and news of the Unischedule App. This feature keeps users informed and connected with the latest developments relevant to their interests and activities.

**Related:** [Flutter#142](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/142) - [Flutter#133](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/133)

https://github.com/ISIS3510-202410-Team-13/Flutter/assets/69651671/c2c3ce6c-da7c-464f-925e-c8df901bb2bc

3. **Peer-to-peer Chat**

This new feature enables seamless communication between users within the UniSchedule app. Users can exchange messages in real-time, facilitating instant communication and quick decision-making. Leveraging Firebase Firestore integration, chat messages are securely stored, ensuring reliability and data integrity.

**Related** [Flutter#152](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/152) - [Flutter#153](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/153) - [Flutter#154](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/154)

https://github.com/ISIS3510-202410-Team-13/Wiki/assets/68788933/2c588a1f-3e14-4677-8a13-01b57e818661

# Business Questions (BQs)

> We have re-numbered the BQs according to the final Analytics Dashboard. Some were also slightly modified to reflect the things we learned in the process, including which insights would be the most relevant to learn from our users!

## Type 1: Crashlytics and Telemetry

### BQ 1.1
**Question**: What are the most reported bugs in UniSchedule?  
**Relevance**: This question is essential for maintaining the quality and reliability of the app. By identifying the most frequently reported bugs, the development team can prioritize fixes that will have the most significant impact on user experience and satisfaction.  
**Type Justification**: This question is categorized under Type 1 because it relies on crash reports and telemetry data to identify recurring issues within the app. Understanding these bugs allows for targeted improvements and a more stable application.  
**Sprint Developed**: 2

### BQ 1.2
**Question**: Which manufacturers report the most amount of bugs?  
**Relevance**: Knowing which device manufacturers are associated with the most bugs can help the development team focus on optimizing the app for those specific devices. This can lead to better performance and fewer issues for a significant portion of the user base.  
**Type Justification**: This question falls under Type 1 as it uses telemetry data to analyze and identify patterns in bug reports based on device manufacturers. This data-driven approach helps in targeting the most problematic areas.  
**Sprint Developed**: 3

### BQ 1.3
**Question**: Which Operative Systems report the most amount of bugs?  
**Relevance**: Identifying which operating systems report the most bugs can guide the development team to address OS-specific issues, ensuring better compatibility and performance across different platforms.  
**Type Justification**: This is a Type 1 question because it leverages telemetry and crash report data to analyze the frequency and nature of bugs across different operating systems, facilitating targeted troubleshooting and enhancements.  
**Sprint Developed**: 3

### BQ 1.4
**Question**: Which device models report the most amount of bugs?  
**Relevance**: By pinpointing which device models experience the most bugs, the development team can prioritize testing and optimization for these devices, improving overall user experience and reducing frustration for a large user base.  
**Type Justification**: This question is categorized under Type 1 as it focuses on analyzing telemetry data to understand bug reports based on specific device models, enabling more precise and effective improvements.  
**Sprint Developed**: 3

### BQ 1.5
**Question**: Which versions of UniSchedule app report the most bugs?  
**Relevance**: Understanding which app versions report the most bugs can help the development team identify and fix version-specific issues. This ensures that new releases are stable and previous issues are resolved.  
**Type Justification**: This is a Type 1 question because it involves analyzing telemetry and crash report data across different app versions to track and address bugs, ensuring continuous improvement and stability.  
**Sprint Developed**: 4

### BQ 1.6
**Question**: What is the trend behind the amount of bugs reported during the last week?  
**Relevance**: Tracking the trend of bug reports over the last week helps in identifying new or escalating issues promptly, allowing for quick fixes and maintaining a high level of app performance and reliability.  
**Type Justification**: This question is categorized under Type 1 as it relies on telemetry data to monitor and analyze the trend of bug reports, providing insights for timely interventions and quality assurance.  
**Sprint Developed**: 4

## Type 2: User Experience

### BQ 2.1
**Question**: Which university majors spend the most time per scheduled meeting?  
**Relevance**: This information can help tailor features and resources to specific majors, improving their user experience by understanding their unique needs and usage patterns.  
**Type Justification**: This question is Type 2 because it focuses on user behavior to enhance their experience by providing insights that can be used to customize the app's functionality for different user groups.  
**Sprint Developed**: 2

### BQ 2.2
**Question**: At which times and days of the week do users schedule the most meetings?  
**Relevance**: Identifying peak times for meetings can help in optimizing app performance during these periods and ensuring that the app can handle high traffic efficiently.  
**Type Justification**: This question falls under Type 2 as it aims to improve user experience by understanding and accommodating users' scheduling habits and preferences.  
**Sprint Developed**: 2

### BQ 2.3
**Question**: Which user type scheduled the most amount of meetings in the last week?  
**Relevance**: Knowing which user types are the most active helps in tailoring support and features to meet the needs of these users, enhancing their overall experience with the app.  
**Type Justification**: This is a Type 2 question because it focuses on user engagement and behavior to improve the app's usability and satisfaction for different user types.  
**Sprint Developed**: 2

### BQ 2.4
**Question**: Which university buildings ranked the best during last week meetings?  
**Relevance**: Identifying top-ranked buildings can help in promoting these locations to other users and understanding what features or characteristics make them popular.  
**Type Justification**: This question is Type 2 as it seeks to enhance user experience by leveraging feedback to highlight and replicate successful meeting locations.  
**Sprint Developed**: 2

### BQ 2.5
**Question**: What is the average availability score per building during the last week?  
**Relevance**: This helps in identifying buildings with high or low availability, allowing for better planning and allocation of resources to improve user experience.  
**Type Justification**: This question is categorized under Type 2 because it focuses on user feedback and behavior to improve the functionality and accessibility of university buildings.  
**Sprint Developed**: 2

### BQ 2.6
**Question**: What is the distribution of user-provided ratings within the app?  
**Relevance**: Understanding how users rate different aspects of the app provides insights into areas that are performing well and those that need improvement.  
**Type Justification**: This is a Type 2 question as it uses user feedback to enhance the overall experience by addressing concerns and improving high-rated features.  
**Sprint Developed**: 2

### BQ 2.7
**Question**: What is the average satisfaction of each type of user?  
**Relevance**: Knowing the average satisfaction levels of different user types helps in customizing the app to better meet their needs and increase overall satisfaction.  
**Type Justification**: This question is Type 2 because it analyzes user feedback to improve the experience for different user demographics.  
**Sprint Developed**: 3

### BQ 2.8
**Question**: How has the user satisfaction score changed over time?  
**Relevance**: Tracking changes in user satisfaction over time helps in assessing the impact of updates and changes, guiding future improvements.  
**Type Justification**: This question falls under Type 2 as it involves monitoring user feedback trends to continually enhance the app's user experience.  
**Sprint Developed**: 3

### BQ 2.9
**Question**: How do users rate the place recommendations service?  
**Relevance**: User ratings of the place recommendations service can guide enhancements to this feature, ensuring it meets user expectations and improves overall satisfaction.  
**Type Justification**: This question is categorized under Type 2 because it focuses on user feedback regarding a specific feature to improve its usability and effectiveness.  
**Sprint Developed**: 3

### BQ 2.10
**Question**: Which on-campus buildings did users rate the best for available spaces?  
**Relevance**: This helps in identifying the best-rated buildings for available spaces, guiding other users and informing improvements to less-rated buildings.  
**Type Justification**: This question is Type 2 because it leverages user feedback to enhance the overall user experience by promoting highly rated locations.  
**Sprint Developed**: 4

## Type 3: Feature Usage

### BQ 3.1
**Question**: Which cities do users log-in from the most?  
**Relevance**: Understanding the geographic distribution of users helps in tailoring features, marketing efforts, and support to those regions, improving user satisfaction and engagement.  
**Type Justification**: This is a Type 3 question because it analyzes feature usage based on user location, providing insights for targeted improvements and support.  
**Sprint Developed**: 3

### BQ 3.2
**Question**: How many unique users have we reached so far?  
**Relevance**: Knowing the number of unique users helps in understanding the app's reach and growth, informing marketing and development strategies.  
**Type Justification**: This question falls under Type 3 as it focuses on metrics related to user engagement and reach, which are critical for evaluating the app's performance.  
**Sprint Developed**: 3

### BQ 3.3
**Question**: What is the average number of days that users have been using the app?  
**Relevance**: Understanding user retention helps in evaluating long-term engagement and identifying areas for improvement to keep users active.  
**Type Justification**: This is a Type 3 question as it delves into usage duration metrics to assess and enhance user engagement over time.  
**Sprint Developed**: 4

### BQ 3.4
**Question**: How many user events have we captured within the app over time?  
**Relevance**: Tracking user events helps in understanding engagement and usage patterns, informing future development and feature enhancements.  
**Type Justification**: This question is categorized under Type 3 as it focuses on the accumulation of usage data to evaluate and improve user engagement.  
**Sprint Developed**: 4

## Type 4: Monetization

### BQ 4.1
**Question**: How much time do users spend in UniSchedule per session?  
**Relevance**: This helps in understanding user engagement, identifying opportunities to enhance session duration, and potentially increasing monetization through ads or premium features.  
**Type Justification**: This is a Type 4 question because it relates to monetization by analyzing user engagement and session duration, which are key metrics for revenue generation.  
**Sprint Developed**: 2

### BQ 4.2
**Question**: Which views do users spend the most time in?  
**Relevance**: Identifying the most engaging views can guide feature improvements, content placement, and advertising strategies to maximize user interaction and monetization opportunities.  
**Type Justification**: This question falls under Type 4 as it focuses on user engagement metrics that can inform monetization strategies and enhance feature usage.  
**Sprint Developed**: 2

### BQ 4.3
**Question**: What is the trend behind the average duration per session in the last month?  
**Relevance**: Understanding trends in session duration helps in assessing engagement levels and the impact of recent updates, guiding future improvements to maximize user retention and monetization.  
**Type Justification**: This is a Type 4 question because it tracks user engagement trends, which are crucial for evaluating the app's performance and optimizing monetization strategies.  
**Sprint Developed**: 3

### BQ 4.4
**Question**: What is the change in the distribution of visited pages within the last month?  
**Relevance**: Analyzing changes in page visits helps in understanding user interests and optimizing content placement and navigation, enhancing user experience and monetization potential.  
**Type Justification**: This question is categorized under Type 4 as it focuses on user engagement metrics to inform content strategy and monetization efforts.  
**Sprint Developed**: 4

## Type 5: Cross-category

> Here we highlight the BQs that we classified as Type 5, which means that they can belong to more than one category. Notice we mentioned them previously because we followed the structure of the Analytics Pipeline; however, we also included them in this special section to differentiate them from the rest.

### BQ 2.1 (Also Type 4)
**Question**: Which university majors spend the most time per scheduled meeting?  
**Relevance**: This insight can help tailor features and resources to specific majors, improving their user experience by understanding their unique needs and usage patterns. Additionally, it can inform targeted advertising and premium offerings for high-engagement majors.  
**Type Justification**: This question is both Type 2 and Type 4 because it aims to enhance user experience by understanding usage patterns and leveraging these insights for monetization through targeted ads or premium content.  
**Sprint Developed**: 2

### BQ 2.2 (Also Type 4)
**Question**: At which times and days of the week do users schedule the most meetings?  
**Relevance**: Identifying peak times for meetings can help in optimizing app performance during these periods and ensuring that the app can handle high traffic efficiently. Additionally, understanding these patterns can guide the placement of ads or promotions during high-usage periods.  
**Type Justification**: This question falls under both Type 2 and Type 4 as it seeks to enhance user experience through understanding scheduling patterns and leveraging these insights for monetization.  
**Sprint Developed**: 2

### BQ 2.4 (Also Type 4)
**Question**: Which university buildings ranked the best during last week meetings?  
**Relevance**: Identifying top-ranked buildings can help in promoting these locations to other users and understanding what features or characteristics make them popular. Additionally, these insights can guide advertising and sponsorship opportunities within these popular locations.  
**Type Justification**: This question is both Type 2 and Type 4 as it aims to improve user satisfaction by highlighting successful meeting locations and exploring monetization opportunities through promotions and sponsorships.  
**Sprint Developed**: 2

### BQ 3.1 (Also Type 4)
**Question**: Which cities do users log-in from the most?  
**Relevance**: Understanding the geographic distribution of users helps in tailoring features, marketing efforts, and support to those regions, improving user satisfaction and engagement. Additionally, it can guide regional marketing and monetization strategies.  
**Type Justification**: This is both Type 3 and Type 4 because it analyzes feature usage based on user location, providing insights for targeted improvements and monetization strategies.  
**Sprint Developed**: 3

### BQ 3.2 (Also Type 4)
**Question**: How many unique users have we reached so far?  
**Relevance**: Knowing the number of unique users helps in understanding the app's reach and growth, informing marketing and development strategies. Additionally, it aids in evaluating the app's market penetration and potential for monetization.  
**Type Justification**: This question falls under both Type 3 and Type 4 as it focuses on metrics related to user engagement and reach, critical for evaluating the app's performance and monetization potential.  
**Sprint Developed**: 3

### BQ 3.3 (Also Type 4)
**Question**: What is the average number of days that users have been using the app?  
**Relevance**: Understanding user retention helps in evaluating long-term engagement and identifying areas for improvement to keep users active. Additionally, it provides insights into user loyalty and potential for monetization through long-term engagement.  
**Type Justification**: This is both Type 3 and Type 4 because it delves into usage duration metrics to assess and enhance user engagement and inform monetization strategies.  
**Sprint Developed**: 4

### BQ 3.4 (Also Type 4)
**Question**: How many user events have we captured within the app over time?  
**Relevance**: Tracking user events helps in understanding engagement and usage patterns, informing future development and feature enhancements. Additionally, it provides data for targeted marketing and monetization strategies.  
**Type Justification**: This question is both Type 3 and Type 4 as it focuses on the accumulation of usage data to evaluate and improve user engagement and inform monetization strategies.  
**Sprint Developed**: 4

### BQ 4.1 (Also Type 3)
**Question**: How much time do users spend in UniSchedule per session?  
**Relevance**: This helps in understanding user engagement, identifying opportunities to enhance session duration, and potentially increasing monetization through ads or premium features. Additionally, it provides insights into how users interact with the app.  
**Type Justification**: This is both Type 4 and Type 3 because it relates to monetization by analyzing user engagement and session duration and understanding feature usage.  
**Sprint Developed**: 2

### BQ 4.2 (Also Type 3)
**Question**: Which views do users spend the most time in?  
**Relevance**: Identifying the most engaging views can guide feature improvements, content placement, and advertising strategies to maximize user interaction and monetization opportunities. Additionally, it helps in understanding how users navigate the app.  
**Type Justification**: This question falls under both Type 4 and Type 3 as it focuses on user engagement metrics that can inform monetization strategies and feature usage analysis.  
**Sprint Developed**: 2

### BQ 4.3 (Also Type 3)
**Question**: What is the trend behind the average duration per session in the last month?  
**Relevance**: Understanding trends in session duration helps in assessing engagement levels and the impact of recent updates, guiding future improvements to maximize user retention and monetization. Additionally, it provides insights into how changes in the app affect user behavior.  
**Type Justification**: This is both Type 4 and Type 3 because it tracks user engagement trends for monetization analysis and provides insights into feature usage patterns.  
**Sprint Developed**: 3

### BQ 4.4 (Also Type 3)
**Question**: What is the change in the distribution of visited pages within the last month?  
**Relevance**: Analyzing changes in page visits helps in understanding user interests and optimizing content placement and navigation, enhancing user experience and monetization potential. Additionally, it provides insights into user navigation and engagement patterns.  
**Type Justification**: This question is both Type 4 and Type 3 as it focuses on user engagement metrics to inform content strategy and monetization efforts, and feature usage analysis.  
**Sprint Developed**: 4

# Implemented Eventual Connectivity Strategies

> Check out the strategies we implemented in previous sprints [here](https://github.com/ISIS3510-202410-Team-13/Wiki/wiki/S3_Final#eventual-connectivity-scenarios)!

Our eventual connectivity strategies in Sprint 4 include several key components to ensure a seamless user experience, even in offline scenarios:

* **Notification Handling**: When the device is offline, a special connectivity notification is displayed at the top of the notification list, informing the user about the lack of internet connection and its potential impact on missing new notifications. This is implemented through the `ConnectivityNotification` class and integrated within the notifications view.

* **Chat Handling**: When the device is offline, a special connectivity notification is displayed at the top of the Chat list, informing the user about the lack of internet connection and its potential impact on missing new messages. Unsent messages are saved in a queue and will be sent as soon as internet connection becomes available again.

* **Group Creation**: In the group creation functionality, we now preemptively check the internet connection before allowing the user to proceed with creating a group. If there is no internet connection, the option to create a group is disabled. Additionally, the button undergoes a visual transformation—changing its color and text—to clearly indicate to the user that group creation requires an internet connection. This preemptive check is crucial as creating a group involves multiple database operations that could impact several users, thereby necessitating reliable connectivity to ensure data consistency and prevent potential conflicts.

* **Local Storage for Notifications**: Notifications are stored in local storage using Hive. This ensures that users can access their notifications even when offline. New notifications received while offline are saved locally and displayed the next time the app is opened.

* **Local Storage for Chats**: Chats information is stored in local storage using Hive. This ensures that users can access their messages even when offline. New messages received while offline are saved locally and displayed the next time the app is opened.


**Related:** [Flutter#146](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/146) - [Flutter#151](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/151) - [Flutter#154](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/154)

https://github.com/ISIS3510-202410-Team-13/Flutter/assets/78111224/80f069dc-5aca-4f5e-84f0-47fd6575697c

https://github.com/ISIS3510-202410-Team-13/Flutter/assets/69651671/647d0867-fd2b-4680-a1f1-8280d63158f8

https://github.com/ISIS3510-202410-Team-13/Wiki/assets/68788933/c90d915a-1aa9-4490-8ecc-bad79bb1e7c7

# Implemented Local Storage Strategies

> Check out the strategies we implemented in previous sprints [here](https://github.com/ISIS3510-202410-Team-13/Wiki/wiki/S3_Final#implemented-local-storage-strategies)!

In our application, implementing local storage strategies is crucial for enhancing offline functionality and providing a seamless user experience, even in the absence of an internet connection. Here’s a detailed breakdown of our local storage implementation for Sprint 4:

* **Notifications**: Notifications are stored locally using Hive. This allows users to access their notifications offline. When the device regains connectivity, any new notifications are synchronized and displayed.

* **Chat**: Chats are stored locally using Hive. The chat messages, participants information and last typed text are included in the Hive Box. This allows users to read their chats offline. Users can send new messages while offline, which are promptly notified as soon as connectivity comes back and all the new data is updated in the database.

* **Efficiency and Performance**: Accessing data from local storage is significantly faster than fetching it over the internet. This leads to quicker load times and a smoother user experience.

* **Reliability and Data Integrity**: Users can rely on the app to function effectively even when offline. By syncing data whenever an internet connection is available, we ensure that the user's information remains up-to-date.

#### **Advantages of This Approach:**
1. **Enhanced Performance**: Accessing data from local storage is significantly faster than fetching it over the internet, leading to quicker load times and a smoother user experience.
2. **Reliability**: Users can rely on the app to function effectively even when they are offline, which is crucial for mobile applications where constant connectivity cannot be guaranteed.
3. **Data Integrity**: By syncing data whenever the internet connection is available, we ensure that the user's information remains up-to-date across all devices.

**Related:** [Flutter#144](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/144) - [Flutter#154](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/154)

https://github.com/ISIS3510-202410-Team-13/Flutter/assets/78111224/b97ca199-e98b-45f5-b397-804de19dcdf4

https://github.com/ISIS3510-202410-Team-13/Wiki/assets/68788933/9d984c5f-c463-46ca-bcbc-dcc403104160

# Implemented Multithreading Strategies

> Check out the strategies we implemented in previous sprints [here](https://github.com/ISIS3510-202410-Team-13/Wiki/wiki/S3_Final#implemented-multi-threading-strategy)!

In this Sprint, we further enhanced our multi-threading approach by introducing a dedicated "Background Thread" for various services within our application. This thread continuously monitors external events, ensuring immediate interaction within the app without disrupting ongoing user activities. A key implementation includes a background thread that remains vigilant for external notifications, such as the launch of new features. When such events occur, the application is promptly notified, allowing for seamless communication to the user. Likewise, our Chat features use Streams to update themselves based on changes detected in Firestore documents automatically. This strategy ensures that our application can handle these events efficiently without blocking the main thread, thus maintaining a smooth and responsive user experience.

Related: [Flutter#142](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/142) - [Flutter#154](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/154)

https://github.com/ISIS3510-202410-Team-13/Flutter/assets/69651671/c2c3ce6c-da7c-464f-925e-c8df901bb2bc


# Implemented Caching Strategies

> Check out the strategies we implemented in previous sprints [here](https://github.com/ISIS3510-202410-Team-13/Wiki/wiki/S3_Final#implemented-caching-strategies)!

The caching strategy we implemented in Sprint 4 involves storing images and text in notifications and chats to enhance application performance and support eventual connectivity. Here’s a detailed breakdown:

* **Image Caching**: We integrated the `cached_network_image` package to cache images used in notifications and chats. This ensures that images are loaded quickly and are available even when the device is offline.
  
* **Performance Improvement**: Caching images reduces the load on the network and accelerates image rendering, providing a better user experience.

* **Offline Support**: Cached images are available when the device is offline, ensuring that the notifications and chat views remain functional and visually complete.

* **Cache typed text in Chat**: To enhance UX, we cache the text typed by the user on each different chat it has. This way, even if the app closes unexpectedly or the user loses connectivity, it can stay calmed knowing that the app will remember its message the next time it opens the app.

**Related:** [Flutter#149](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/149) - [Flutter#154](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/154)


https://github.com/ISIS3510-202410-Team-13/Wiki/assets/68788933/f84f785b-c971-4a4c-890b-8996eef082fa




# Ethics Video

[Ethics Video Sprint 4](https://youtu.be/iG4vrSW6yY4)
# Sprint 4 Contributions
## David Santiago Ortiz

- Add New Group View - [Flutter#134](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/134)
- Implement Background Thread for External Notifications - [Flutter#142](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/142)
- Implement Group Creation Feature - [Flutter#148](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/148)
- Enhance Group Creation with ECs - [Flutter#151](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/151)

## Juan Esteban Cuéllar

- Implement Notification View with Custom Widgets - [Flutter#133](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/133)
- Add Local Storage for Notifications - [Flutter#144](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/144)
- Improve Connectivity Handling in Notifications View - [Flutter#146](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/146)
- Implement Image Caching for Notifications - [Flutter#149](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/149)

## Juan Sebastian Urrea

- Develop Place Recommendation Analytics - [Flutter#130](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/130)
- Create Chat View Interface - [Flutter#152](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/152)
- Implement Chat Features (Send and Receive Messages) - [Flutter#153](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/153)
- Enhance Chat with Connectivity, Local Storage, and Caching - [Flutter#154](https://github.com/ISIS3510-202410-Team-13/Flutter/pull/154)
