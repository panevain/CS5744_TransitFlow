+++
title = "Use Cases"

sort_by = "weight"
weight = 1
+++

## Anna's Daily Commute to Campus with Blacksburg Transit

**Actor**: Anna, a third-year undergraduate student majoring in Biology at Virginia Tech

**Goal**: Anna needs to use the Blacksburg Transit mobile app for her daily commute between her residence and the university campus.

**Preconditions**:

* Anna has a smartphone with the BT app installed.
* Anna is able to get to a BT stop.

**Scenario**:

1. Anna prepares for her journey on the BT by opening the app half an hour before her first class of the day.
1. She finds the stop nearest to her residence using the map of all active routes.
1. Her stop is serviced by two routes, HWA and HWB. She views both estimated arrival times and selects the next departure on HWA.
1. She waits inside until five minutes before the bus arrives.
1. She walks outside and waits at the stop. While waiting, she views the bus' location on the map as it approaches.
1. The bus arrives and she boards. She waits on the bus until it arrives at her stop.
1. Once the bus arrives at the stop closest to her class, she exits the bus and heads to class.

**Postconditions**:

* Anna successfully and safely used the BT to get to class.

**Alternate Scenario**:

1. Anna was late leaving her residence and missed the HWA bus.
1. She opens the BT app and checks the arrival time of HWB.
1. She waits at the stop for HWB to arrive.

## John's Research using Blacksburg Transit Ridership and Usage Data

**Actor**: John, a transportation planning engineer at the Virginia Tech Transportation Institute (VTTI)

**Goal**: John needs to gather information about how Virginia Tech students travel around town on days with Football games

**Preconditions**:

* John has access to a computer with a web browser.
* John has access to statistical analysis tools.

**Scenario**:

1. John visits the Virginia Tech athletics website to gather a list of days with home Football games
1. John loads the BT website and navigates to the historical data section.
1. He requests the hourly passenger pickups at each stop on days with Football games.
1. He specifies that the returned data should be in the JSON format.
1. The system tabulates the data and returns the JSON file to John.
1. John also requests a JSON file containing the latitude and longitude of each bus stop in the system.
1. The system returns the data as a JSON file.
1. John uses the JSON data to identify patterns and trends in passenger trips.

**Postconditions**:

* John has successfully gathered data related to how Virginia Tech students travel around town on football game days, incorporating hourly passenger data from the BT website.

## Janice's System Management using the Administrative Web Application

**Actor**: Janice is a BT system operator.

**Goal**: Janice needs to add information about a temporary change in route for a bus route while alerting riders to the change.

**Preconditions**:

* Janice has access to a computer with a web browser.
* Janice is an authorized administrative user with valid credentials.

**Scenario**:

1. Janice loads the BT administrative web application and logs in.
1. Janice navigates to the alert section.
1. She creates a new alert and enters the start time, end time, affected route and affected stops.
1. She saves the alert and navigates to the route section.
1. She selects the route and creates a temporary detour.
1. She enters the new stops and adds waypoints which are rendered on the map.
1. She saves the temporary detour and exit the application.

**Postconditions**:

* Janice's modifications to the route are reflected in the mobile, web, and text messaging interfaces.
* BT riders are alerted to the temporary change in the route in a clear and timely manner. Passengers can plan their journeys accordingly and adapt to the new route, minimizing disruptions.