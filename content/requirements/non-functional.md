+++
title = "Non-Functional Requirements"

sort_by = "weight"
weight = 4
+++

* **NFR-1**: The application should be available 99.99% of the time.
* **NFR-2**: The application should always be available during peak times (approximately 8am to 4 pm).
* **NFR-3**: The application should automatically scale to support increased user numbers during peak usage times.
* **NFR-4**: The application, be it the web application or mobile application, should load the live map within 2 seconds.
* **NFR-5**: Any historical data query should be fulfilled and the data supplied to the user within 10 seconds.

Quantify user numbers at peak load
Quantify end-to-end time to pass data from bus to user map
Bus states are logged into the central DB every X seconds