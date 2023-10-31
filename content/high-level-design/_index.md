+++
title = "High Level Design"

sort_by = "weight"
weight = 3
+++

<!--
Devise and present the high-level **design** of the system. Use diagrams that
are appropriate for the design approach your team is practicing.
-->

The core of the application is data. Ultimately, the objective of TransitFlow is
to deliver real-time data from busses to Blacksburg Transit users.

Because of this, the approach taken to collect, analyze, and disseminate data has
major implications for the design and ultimate success of the application.

## Layered Approach
### Data Collection Layer
This layer sees raw data being collected from sources physically on the bus.
In this form, the data is meaningless to the end user, but is the foundation of
the application.

As the data is collected by sources on the bus, it is sent to the server for
processing and persistent storage. As long as the busses are in operation, it
is paramount that the server is available to receive data.

The sources of the data on the busses may be any number of devices, including
interfaces that the driver of the bus interacts with. Alternatively, the data
may be collected by a device that passively collects data from the bus, like
a GPS locator or speedometer.

### Refinement Layer
Although the data remains in it's most raw form in the database, the API layer
provides an interface to other portions of the application to access the data
in a more meaningful and enriched form.

This layer is responsible for combining the raw data and the context in which
that data was collected to provide a more useful representation of the data.
For example, the database might store the following data points:
- Your location is currently stop number 1115
- Bus 157 is currently between stops 1112 and 1113
- Bus 157 currently has 16 passengers
- Bus 157 still has to make stops at 1113 and 1114 before reaching your stop
- At this time of the day:
  - Stop 1113 has an average of 5 passengers boarding
  - Stop 1113 has an average of 2 passengers exiting
  - Stop 1114 has an average of 15 passengers boarding
  - Stop 1114 has an average of 10 passengers exiting
  - Stop 1115 has an average of 17 passengers boarding
  - Stop 1115 has an average of 3 passengers exiting
- Bus 157 is a 40-foot non-articulated bus that can hold 80 passengers

Without further introspection, the data is not very useful at a glance.
However, the API can provide business logic to produce more meaningful data.
For example, the following could be concluded:
- Bus 157 is expected to have about 28 passengers when it reaches your stop, about 35% of it's capacity
- Bus 157 is expected to have about 42 passengers as it leaves your stop, about 52% of it's capacity
- There will be plenty of room on the bus for you to board at your stop

Although this example is contrived, it demonstrates the power of the API layer.
The API will be client agnostic, meaning that it will be able to provide data
consistently to any client that requests it, regardless of how the client ends
up using the data.

### Presentation Layer
Even after contextualized data is produced by the API layer, it may still lack
human-readability. This is especially true for geographical data; latitude and
longitude coordinates are not very useful to most users.

Because of this, the an additional layer is required to polish the data for
presentation to the user. In the example of geographical data, this layer would
be responsible for taking coordinates and producing points on a map, possibly
connecting multiple points to form a path - like a bus route.