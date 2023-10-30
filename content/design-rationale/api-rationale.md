+++
title = "API"

sort_by = "weight"
weight = 2
+++

### DAO Pattern

The use of the DAO pattern allows for users to access the system in a simple and secure way. Because all database transactions are handled by the DAO object, there is no risk for users inadvertently - or purposefully - causing damage to the database. Additionally, there is no need for users to write their own queries, since the DAO object handles those, so users do not need to learn the database structure in order to retrieve the data they desire.

### Why HTTP and REST?

HTTP has become the standard communication protocol for most internet transactions, so having the TransitFlow API use HTTP methods ensures that the API is as accessible as possible. Also, since HTTP has been in use for so long and is so widespread, it is very well tested and has proven incredibly reliable, so there is reasonable trust that we will not have uptime concerns because of failure in our data transfer protocol. 

The TransitFlow API uses the REST architecture to structure its functionality because of the ease of use it ensures for users. Having request format be standardized ensures that users can easily access all of the API endpoints without concern for varying request formats that would increase the difficulty they encounter. REST was also chosen because of its statelessness, ensuring that all transactions occur server-side rather than client-side, keeping the database secure and reducing compute cost for users. 

### Choice of HTTP Methods

All public access points of the API utilize the GET method of HTTP. This is because it allows for data to be retrieved easily and securely with minimal risk that the user can inject something unwanted into the system. 

For all other transactions, the HTTP methods POST or DELETE are used. This is because all other transactions require valid credentials to accomplish, and POST and DELETE both allow for request bodies, which can carry credential information to be validated by the system. These also allow for the request to carry information about what data is being modified, created, or deleted by the action the user is requesting.

