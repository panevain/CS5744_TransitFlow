+++
title = "Back End"

sort_by = "weight"
weight = 2
+++

Server architectures are crucial in defining the efficiency, scalability, and reliability of web applications. The architecture for the proposed system is designed to handle requests efficiently, manage data securely, and provide a flexible structure for future expansion. The system's architecture is composed of several key components: Server, API, Cache, DatabaseConnection, ClientFormatter, and AdminWebApp. Each component plays a vital role in the system's overall functionality.

### Server

The Server acts as the central hub for managing requests and orchestrating the interactions between different components. It contains references to the API, DatabaseConnection, and Cache, ensuring that all parts of the system are accessible from a central point. The `processRequest` operation allows the Server to handle incoming requests and delegate them to the appropriate components based on the request type and data.

### API

The API serves as the gateway for external communications and is divided into multiple endpoints: webEndpoint, mobileEndpoint, smsEndpoint, and adminEndpoint. This modular approach allows for specialized handling of different types of requests, enhancing the system's flexibility and scalability. The `handleRequest` operation in the API ensures that each endpoint can process requests independently, providing a clean separation of concerns.

### Endpoint

Each Endpoint (web, mobile, sms, and admin) is designed to handle specific types of requests, characterized by its path and request type (GET, POST, etc.). This design allows for a more organized and manageable way of processing requests, where each endpoint can be optimized for its specific purpose.

### Cache

The Cache is a critical component for improving the performance of the system. It stores frequently accessed data, reducing the load on the database and speeding up response times. The operations `addToCache` and `getFromCache` ensure that data can be stored and retrieved efficiently, providing a significant boost to the system's performance.

### DatabaseConnection

The DatabaseConnection is responsible for all interactions with the database, encapsulating data storage and retrieval. Its operations, `storeData` and `retrieveData`, abstract the complexity of database operations, providing a simple interface for the Server and API to interact with the database.

### ClientFormatter

The ClientFormatter is used for formatting data for different client types - web, mobile, and SMS services. This component ensures that the data is presented in the most suitable format for each client, enhancing the user experience and ensuring compatibility across different devices and platforms.

### AdminWebApp

The AdminWebApp is a specialized component designed for administrative tasks such as updating routes, buses, stops, and alerts. It interacts directly with the API, providing a user interface for system administrators to manage the application's data and settings.

{{ image(figure_number=1,
caption="Unified Modeling Language (UML) Diagram depicting TransitFlow back-end.",
src="./server-uml.png",
alt="A series of interconnected tables describing the database design for the TransitFlow application.")}}
