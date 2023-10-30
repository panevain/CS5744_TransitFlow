+++
title = "Web Application"

sort_by = "weight"
weight = 3
+++

### Overall Rationale

The one non-public interface is intended for system operators to create, read, update, and delete information which is served to public clients. Each of these operations can be accomplished by connecting to the database and writing SQL, but this is a high barrier to entry and risks damage to the data stored within. Each endpoint uses a DAO on the server-side to encapsulate the SQL operations being performed. Each endpoint can be triggered by a UI interaction, thereby reducing the complexity of interfacing with the system.

The web app allows system operators to log in using their credentials. Their login credentials are then stored and passed with every request to an authenticated endpoint. This automation allows the administrative web app to use the same public endpoints as every other client while seamlessly accessing restricted endpoints too.

### Frontend Technology Rationale

Angular is a powerful and extremely popular choice for building the frontend of web applications. It provides a diverse set of tools for building UIs, and has a large community of developers that provide maintenance, upgrades, and documentation for the framework.

Angular is a component-based framework, which allows for the creation and use of reusable components that can be adjusted independently of each other - allowing for a modular application. Many commonly use components such as date pickers, dialog boxes, and layout components are already provided by libraries like Angular Material and can be seamlessly integrated into the application with minimal effort.

Another benefit of Angular is that it supports the use of TypeScript which allows for the application to strongly type it's data as it is passed between components. This powerful feature improves the maintainability of the application and makes it easier for developers to find the source of bugs in the application.

Angular also provides a feature called pipes, which allow for the transformation of data before it is rendered on a component's template. This allows for flexibility of the presentation of data regardless of how it was received or stored. This feature is especially useful for changes in the format of the data that may occur as the application is developed or maintained.
