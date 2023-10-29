+++
title = "Top Level Architecture"

sort_by = "weight"
weight = 1
+++

The combination of new and existing components presents some unique requirements for TransitFlow to be successful. The TransitFlow application is an archetypical three-layer design.

Blacksburg Transit currently offers a web application as well as Android and iOS mobile applications. For accessability reasons, BT also offers a SMS-based interface. This SMS interface offers limited functionality for those without smartphones or internet access outside of their homes. These four public interfaces constitute the primary presentation layer. These interfaces consume the same raw data, but each may offer different functionality in the future. Concurrently, BT system operators have a secondary presentation layer via a [web application](@/detailed-design/web-application-design.md). This web application allows them to modify information within the system including the buses, routes, stops, alerts, and trips being provided to users.

The application layer consists of an [application server and one or more caches](@/detailed-design/back-end-design.md). All public interfaces only read information, meaning that few computational resources are necessary to generate the data that clients require. The number of caches can be scaled up and down as user demand fluctuates. System operators are able to modify the application state through their secondary interface. Public interfaces pull data via multiple [API endpoints](@/detailed-design/API-design.md). The [format of the data](@/detailed-design/data-interchange-design.md) being passed between the server and clients is designed to support existing functionality while supporting future behavioral changes.

Finally, the data layer consists of a relational [database](@/detailed-design/database-design.md) which maintains information about the network and past travel history of each bus. The following diagram depicts the high-level organization of the TransitFlow application.

{{ image(figure_number=1,
caption="The high-level design for the TransitFlow application.", 
src="./high-level.png", 
alt="A collection of objects describing the TransitFlow application's high level design.")}}

The [traceability matrix](@/high-level-design/traceability-matrix.md) elaborates on how each components supports the functional and non-functional requirements of the system.