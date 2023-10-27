+++
title = "Data Interchange Design"

sort_by = "weight"
weight = 3
+++

The primary function of TransitFlow is to transfer data from data creators (buses) to data consumers (users on the app). Data in the TransitFlow system goes through a lifecycle that brings it through several different phases, beginning at the buses themselves and ending in long-term data storage servers. Between those stages, the data is sent from the buses to the central system to be stored in the live data cache, from which it can be retrieved by users through a variety of methods. Once the system receives new data from the bus, old data will be evicted from the cache and sent to long-term storage, where it will stay.

### Data Creation:

Data begins life by being generated onboard one of the up to 24 buses that are in use by BT. This data consists of things like bus location in terms of latitude and longitude coordinates, bus heading, speed, most recent stop, number of passengers, and more. This data will also contain a key, which is the bus number. Once the data has been created, it is sent to the central TransitFlow system via an antenna on the roof of each bus.

### Data Processing:

Once data is received by TransitFlow, some processing must occur to standardize the data. BT's bus fleet is far from standardized, and very few of their buses were manufactured at the same time, resulting in buses that have wildly different methods by which they send the data they generate, and equally as different formats by which that data is organized[^1]. Because of this, some processing must occur once the data is received by TransitFlow before it can be sent to users. (PUT MORE ABOUT THIS LATER).

### Data Retrieval:

Once data has been received by TransitFlow and the data processing has occurred, the data will briefly reside in the cache so that it can be retrieved by users. This data will be what is used to populate the live map and show users where buses are, what their last stop was, what route they are on, and how full they are. There are a few different ways that users will be able to retrieve this data: through the mobile application, through the web application, and through the SMS service.

**Mobile Application:**

The primary method by which users currently retrieve information about the bus system is through the BT mobile application. The primary function of this app is to have a live map of all of the buses and the bus routes. This map will be populated by the app requesting the contents of the cache from TransitFlow, which will then be loaded in teh app iteself. The cache will be sent through the internet and retrieved by the mobile device running the application either through Wi-Fi or a cellular network. The data will be sent as a JSON which is structured as an array, and each entry in the array will be the most recent data of a bus. The map itself will not be retrieved from TransitFlow or BT, but rather will be retrieved through the Google Maps API in order to save throughput from the TransitFlow servers. Every 15 seconds, the application will send a request to the server for new data, and the central server will send the contents of the cache again in a new JSON object.

**Web Application:**

Another method by which users may retrieve bus information is through the web application hosted on the BT website, https://ridebt.org. This web application functions similarly to the mobile application, requesting the most recent bus data from the server on start and then sending a request for new data every 15 seconds. Data will again be transferred as a JSON array where each item in the array is the data for a different bus.

**SMS Messaging:**

Not everyone has a smartphone, and may not have access to a computer when they wish to receive bus information, so TransitFlow will provide an SMS system that users can use to retrieve data. This system will use Twilio to send and receive messages. Users can retrieve data by sending a message containing the unique stop code for a stop that they wish to receive information about. The system will receive that message, and using the stop code, will query the most up-to-date route information it has to compile a list of all bus routes that service that stop. The system will also query the route timetables to determine what the next time a bus servicing those routes will arrive at the stop, and include that information in a message sent to the user. All of this information will be sent as text in a text message.

### Long-Term Storage:

Buses are constantly generating new data, and this data is constantly being sent to TransitFlow, so not all of it can be stored in the cache. So, every time a bus sends new data to the system, TransitFlow will evict the most recent information that the bus sent from the cache and insert the new data. The data that was evicted will then be sent to a long-term storage device which will insert the data into a database to be used later.

### API Requests:

TransitFlow will provide a REST API for users to be able to retrieve historical and current data about the BT system. This API will be publically available, and will allow users to query the database to retrieve historical data about one or more bus, route, stop, or combination of the three. This data will be organized in a JSON object that will be sent to the user using HTTP, allowing the user to handle the data as they wish. The API will also provide a method by which users can open a connection to receive a JSON containing the contents of the live data cache every 15 seconds.

### Load Handling:

With each data access method except for the SMS system, data is sent to users every 15 seconds. This is so that the data that a user sees is as "fresh" as possible, but also on enough of a delay so that the system is not overwhelmed by requests from users. Because peak loads can exceed 10 thousand users, the system will constantly be receiving requests, so having a point of access limited to one request every 15 seconds reduces the amount of requests handled by the system to a reasonable amount in order to reduce the time that a user must wait to have their request fulfilled.



[^1]: [Blacksburg Transit System Information](https://ridebt.org) (From a conversation Matthew Averyt and Matthew Newcomer had with BT customer service employees on 24 October 2023)