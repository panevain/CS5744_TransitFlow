+++
title = "API"

sort_by = "weight"
weight = 3
+++

### REST API

While it is functioning, TransitFlow is collecting massive amounts of data and storing it in long-term storage. The web and mobile applications will not have access to this data, but we want users to be able to get the data if possible, so we will provide a REST API that users can use to receive historical data. This API will be used by users to retrieve data stored in the database, but will also be used by admin users to set, update, and delete data from the database. This API will use the Data Access Object (DAO) pattern to function.

### DAO Pattern

Each DAO object will be paired with a model object that will represent a real-world object, such as a bus or route, that is present in the database. This DAO object will act as a communication pathway for the users or admins to interact with the database without directly touching the data objects.

{{ image(figure_number=1,
caption="The DAO pattern",
src="./DAO_Diagram.png",
alt="A diagram representing the DAO pattern.")}}

### Interactions:

* User-DAO Object: The user interacts directly with DAO objects when getting or posting data to the API.
* User-Model Object: The user interacts with the model object when retrieving data, modifying existing data, or creating new data to enter into the database.
* Interface-DAO Object: The Interface defines the required functionality for each DAO object, ensuring the user can easily interact with all DAO objects, regardless of what they represent.
* DAO Object-Model Object: The DAO object creates model objects after reading information from the database, and reads from model objects when they are modified or when the user creates a new model object.
* DAO Object-Database: The DAO object communicates directly with the database, using predefined queries that the user can use to CRUD the database.
* Model Object-Database: The Model object does not directly interact with the database, but each model object represents a row in the database.

### CRUD Operations

The DAO objects allow for users to create, retrieve, update, and delete (CRUD) from the database without ever directly interacting with the database itself. This ensures that the data is kept safe and not negatively impacted by users accidentally, and also allows users to interact with the database without knowing the database structure or writing their own queries. Below will be diagrams showing how each action occurs in the DAO pattern.

#### Create:

{{ image(figure_number=2,
caption="Create Action in the DAO Pattern",
src="./DAO_create.png",
alt="A diagram representing how the DAO pattern handles creation of records.")}}

Creation of data records begins with the user creating the model object that will represent the row in the database. The user can then set the properties of the model object to whatever they wish. After the user is satisfied with the properties they have set, they can then use the API to inform the DAO object that the model has been created. The DAO object then reads the information from the model object then creates and executes the query needed to insert the data into the database.

#### Retrieve:

{{ image(figure_number=3,
caption="Retrieve Action in the DAO Pattern",
src="./DAO_retrieve.png",
alt="A diagram representing how the DAO pattern handles retrieval of records.")}}

Retrieval begins with the user sending a request to the API for data. The API informs the DAO object that a request was sent so that the DAO object can construct the necessary query to retrieve the desired data. The DAO object then executes the query using the database, and then takes the results of the query and builds a model object for each row retrieved. These model objects are then sent to the user.

#### Update:

{{ image(figure_number=4,
caption="Update Action in the DAO Pattern",
src="./DAO_update.png",
alt="A diagram representing how the DAO pattern handles updating of records.")}}

When a user wishes to update an existing record in the database, they begin by making a modification to a model object that they have reference to. This model object could be one that the user has created, or one that they have retrieved using an earlier API request. Once the user has made the necessary modification, they then send a request to the API containing their updated model object. The API sends that updated object to the DAO object, which uses the updated information to construct and execute the necessary update query to modify the entry in the database.

#### Delete:

{{ image(figure_number=5,
caption="Delete Action in the DAO Pattern",
src="./DAO_delete.png",
alt="A diagram representing how the DAO pattern handles deletion of records.")}}

Deletion begins with the user sending a delete request to the API. The API then sends this request to the DAO object, which constructs and executes the necessary query to delete the data records. No model objects are involved in deletion of records.

### API Access:

Not all of the API is accessible to every user. Only retrieval of records is open to the public, since we do not wish to have regular users modifying the contents of the database. Creation, updating, and deletion of data is accessible only to admin users. 

### API Endpoints:

The following list will contain some, but not necessarily all of, the API endpoints that TransitFlow provides. Some of these endpoints will only be accessible to those with administrator priveleges. 

| HTTP Verb | API Endpoint                                  | Description                                                                       |
|:---------:|-----------------------------------------------|-----------------------------------------------------------------------------------|
|    GET    | /buses/all                                    | Retrieve a list of all buses in the system.                                       |
|    GET    | /buses/active                                 | Retrieve a list of all currently active buses.                                    |
|    POST   | /buses                                        | Creates a new bus. Credentials required.                                          |
|    POST   | /buses/{id}                                   | Modifies an existing bus. Credentials required.                                   |
|   DELETE  | /buses/{id}                                   | Deletes an existing bus. Credentials required.                                    |
|    GET    | /routes                                       | Retrieves a list of all routes in the system.                                     |
|    GET    | /routes/current                               | Retrieves a list of all routes currently being serviced.                          |
|    POST   | /routes                                       | Creates a new route. Credentials required.                                        |
|    POST   | /routes/{id}                                  | Modifies an existing route. Credentials required.                                 |
|   DELETE  | /routes/{id}                                  | Deletes an existing route. Credentials required.                                  |
|    GET    | /patterns/all                                 | Retrieves a list of all patterns in the system.                                   |
|    GET    | /patterns/active                              | Retrieves a list of all patterns currently being serviced.                        |
|    GET    | /patterns/{pattern}/positions                 | Retrieves a list of waypoints and stops for the provided pattern.                 |
|    GET    | /patterns/{pattern}/positions/{id}/prediction | Retrieves the predicted arrival for buses on a given pattern for a specific stop. |
|    POST   | /patterns                                     | Creates a new pattern. Credentials required.                                      |
|    POST   | /patterns/{id}                                | Modifies an existing pattern. Credentials required.                               |
|   DELETE  | /patterns/{id}                                | Deletes an existing pattern. Credentials required.                                |
|    GET    | /trips/{pattern}                              | Retrieves the most recently posted timetable for the provided pattern.            |
|    POST   | /trips                                        | Creates a new trip. Credentials required.                                         |
|    POST   | /trips/{id}                                   | Modifies an existing trip. Credentials required.                                  |
|   DELETE  | /trips/{id}                                   | Deletes an existing trip. Credentials required.                                   |
|    GET    | /alerts                                       | Retrieves all active alerts for the network.                                      |
|    POST   | /alerts                                       | Creates a new alert. Credentials required.                                        |
|    POST   | /alerts/{id}                                  | Modifies an existing alert. Credentials required.                                 |
|   DELETE  | /alerts/{id}                                  | Deletes an existing alert. Credentials required.                                  |