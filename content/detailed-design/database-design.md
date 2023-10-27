+++
title = "Database Design"

sort_by = "weight"
weight = 2
+++


Databases are powerful tools for organizing and querying massive sets of data. The structured data required to implement TransitFlow's functionality is well supported by a relational database. TransitFlow's database uses MySQL due to its reliability, longevity, liberal licensing, and support for spatial data types and queries. 

The design of a database to support TransitFlow's functionality must solve three main problems:

1.  One bus route name may correspond to one or more ordered sets of stops. For instance, Tom's Creek (TOM) runs a weekday route which is roughly rectangular which services campus and points north. Friday nights and on weekends, TOM reroutes to service a larger area. This creates a situation wherein TOM could refer to "Tom's Creek via Washington St." or "Tom's Creek via Progress Street"; both of which run under to TOM route code. 

    Each specific set of stops and waypoints is a called a pattern. The database supports this arrangement by creating a pattern table which stores the pattern's name and the parent route it belongs to. The pattern point table can then reference the pattern's ID as a foreign key. Each pattern point contains a foreign key reference to a physical position and the metadata about the location. Querying the pattern point table with a pattern ID and ordering by the ordinal column will, therefore, return the set of locations the bus passes through and information about each location.

1.  Bus location and status information is not currently stored. On a fixed interval, bus state entries can be created which store the bus' position, passenger count, timestamp and trip identifier. This table can then be queried by route, pattern, bus, trip, stop, or passenger count. 

1.  The trips for the day must be pre-entered and editable. System operators are able to create entries in the trip table which specify the starting and ending pattern points, timestamps, and the bus assigned to the trip. 

{{ image(figure_number=1,
caption="The database schema for the TransitFlow application.", 
src="./db.svg", 
alt="A series of interconnected tables describing the database design for the TransitFlow application.")}}



