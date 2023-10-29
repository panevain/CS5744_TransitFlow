+++
title = "Web Application"

sort_by = "weight"
weight = 4
+++

### Design Decision

User interfaces are one of the most vital parts of a full stack application.
They facilitate the interaction and communication between the user and the application.
Because of this, it is important that the provided interface is clear and easy to use.
Without a reliable, understandable, and powerful UI, the application's usefulness to standard users
is limited by the ability to interact with it. Even if other portions of the application are
well designed, performant, and satisfy all desired requirements, a poor UI can make those features
difficult to interact with, and in some cases may eliminate their usefulness entirely. Additionally,
it is important that a UI is adaptable to easily interface with other application services, even
as those services change over the course of development and maintenance.

Because of this, the UI for the application will be built using the Angular framework. Angular
is a powerful and extremely popular choice for building the frontend of web applications. It
provides a diverse set of tools for building UIs, and has a large community of developers that
provide maintenance, upgrades, and documentation for the framework.

Angular is a component-based framework, which allows for the creation and use of reusable
components that can be adjusted independently of each other - allowing for a modular application.
Many commonly use components such as date pickers, dialog boxes, and layout components are already
provided by libraries like Angular Material and can be seamlessly integrated into the application
with minimal effort.

Another benefit of Angular is that it supports the use of TypeScript which allows for the
application to strongly type it's data as it is passed between components. This powerful feature
improves the maintainability of the application and makes it easier for developers to find the source
of bugs in the application.

Angular also provides a feature called pipes, which allow for the transformation of data before it
is rendered on a component's template. This allows for flexibility of the presentation of data
regardless of how it was received or stored. This feature is especially useful for changes in the
format of the data that may occur as the application is developed or maintained.

### Design Description

As laid out in the __Janice’s System Management using the Administrative Web Application__ scenario,
the web application will be used by administrators like Janice to manage the system. This includes
the ability to recognize some users with elevated privileges (admin users) that have access to
additional features of the application that standard users do not such as adding alerts, stops,
and routes to the system.

The functional requirements for the application also lay out the following requirements for the
administrative web application:
> - FR-12: Administrative users can enter, modify, and delete bus information.
> - FR-13: Administrative users can enter, modify, and delete route information and route stops.
> - FR-14: Administrative users can enter, modify, and delete alerts.

These requirements elicit the need for a UI components that allow for operations that can create, read,
update, and delete (CRUD) application records. These components should be accessible only to users
with designated privileges. Although this user privilege checking will ultimately be done by the backend, it
is also important that these UI components are not made available to users without the proper associations.
This can easily be accomplished using Angular Routing Guards, which introduce the ability to check
if a user is authorized to access a route before the route is loaded. As an admin user, this has
no effect on the user experience. On the other hand, standard users are prevented them from accessing routes.

### UI Components

#### Login Page

The login page will be the first component that users are presented with when they visit the application.
It will be a simple form that allows users to enter their credentials and log in to the application.
It will be available at the `/login` route.

#### Authentication Error Page

The authentication error page will be a component that is displayed when a user attempts to access
a route that they are not authorized to access. It will be a simple page that displays an error message
and a link to the login page. It will be available at the `/error` route. This is the route that users
will be redirected to by the Angular Routing Guard when they attempt to access a route that they are
not privileged to access.

#### Across Admin Pages

Each component will provide a validation step before any data is sent to the backend services. This will
prevent invalid or ill-formatted data from being sent to the backend services. Clear explanations of
validation errors will be provided to the user when encountered. This allows for the user to change the input
to correct the error and resubmit the data without having to re-enter all of the information.

#### Admin Panel

The admin panel will be the first component that administrators are presented with when they log in
to the application. This component is a dashboard that provides links to the various administrative
features. It will be available at the `/manage` route, and will be protected using an Angular Routing Guard.

#### Bus Management

As described in the functional requirements, the application must allow for administrative user to view
and manage bus information. This includes the creation, modification, and deletion of bus information.
This will be accomplished by a set of UI components that allow for the CRUD operations on bus information.
They will be available at the `/manage/bus` route, and will be protected using an Angular Routing Guard.

This page will consist of a table that displays all of the bus information provided by the backend services.
The table will be a paginated Angular Material table that allows for sorting and filtering of the data.
This table will also provide the functionality to click on a single row to view more detailed information.
This will be accomplished by a dialog box that displays the information in a more readable format.
As a part of this dialog box, there will be buttons that allow for the editing and deletion of the given information.
Before the deletion or modification of any information, the user will be prompted to confirm their action.
The information that will be displayed in the dialog box will be are the following:
- Manufacturer
- Model
- Length
- Propulsion
- Purchase Date
- Sold Date (if applicable)
- License Plate

The individual bus information dialog box will also provide a button that view the bus's maintenance records.
This will show the date and description of each maintenance record for the given bus. An option to add a new
maintenance record will also be provided.

The bus management page will also provide a button that allows for the addition of a new bus.
Upon clicking this button, a dialog box will be displayed that allows for the entry of the bus information
in a very similar format to the individual bus information dialog box. If a maintenance record exists for
the new bus, the dialog box will also provide the ability to upload the maintenance record.

#### Route Management

Similarly to the bus management page, the route management page will consist of a table that displays all of
the route information provided by the backend services. The table will be a paginated Angular Material table
that allows for sorting and filtering of the data. This table will also provide the functionality to click on
a single row to view more detailed information. This will be accomplished by a dialog box that displays the
information in a more readable format. As a part of this dialog box, there will be buttons that allow for the
editing and deletion of the given information. Before the deletion or modification of any information, the user
will be prompted to confirm their action. The information that will be displayed in the dialog box will be are
the following:
- Route Name
- Route Short Code
- Route Color
- Route Text color
- Route Pattern (stops, waypoints, timechecks)
- Number of Active Alerts

The dialog box will also provide the capability to manage alerts to the specified route that is being viewed.
When an alert is added, it can have a "lifetime" (start and end) that specifies the time period that the alert is active.
After the lifetime of the alert has expired, the alert will be automatically archived for the given route
meaning it will no longer be visible to users. This dialog box will also provide the ability to edit or delete
alerts that have been added to the route. Confirmation will be required before any of these actions are taken.

The route management page will also provide a button that allows for the addition of a new route.
Upon clicking this button, a dialog box will be displayed that allows for the entry of the route information
in a very similar format to the individual route information dialog box. Alerts on the new route can
be added at this point, or added later using the dialog box.

#### Alert Management

In addition to the alert management capabilities provided by the route management page, the dedicated
alert management page will provide the ability to view and manage all alerts that have been added to the system.
This page will consist of a table that displays all of the active and scheduled alerts for the entire system.
The table will be a paginated Angular Material table that allows for sorting and filtering of the data.
This filtering and sorting behavior will become extremely useful for administrators to rapidly manage alerts
in bulk. This table will also provide the functionality to click on a single row to view more detailed information.
When a table row is clicked, a dialog box that displays the information in a more readable format will be opened.
As a part of this dialog box, there will be buttons that allow for the editing and deletion of the given information.
Before the deletion or modification of any information, the user will be prompted to confirm their action.
The information that will be displayed in the dialog box will be are the following:
- Alert Title
- Alert Message
- Alert Start
- Alert End
- Affected Routes

Because the relationship between alerts and routes is many-to-many, the dialog box will allow admin users
to view and adjust the routes that are affected by the alert. Alerts do not require a route to be specified,
but will not be visible to users until a route is specified.

The alert management page will also provide a button that allows for the addition of a new alert.
Upon clicking this button, a dialog box will be displayed that allows for the entry of the alert information
in a very similar format to the individual alert information dialog box.
