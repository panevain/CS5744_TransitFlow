+++
title = "Non-Functional Requirements"

sort_by = "weight"
weight = 4
+++

* **NFR-1**: The application should be available and able return data to users 99.99% of the time.
* **NFR-2**: The application should always be available during peak times (approximately 8am to 4 pm).
* **NFR-3**: The application should automatically scale to support approximately ten thousand users during peak load.
* **NFR-4**: The application, be it the web application or mobile application, should load the live map within 2 seconds.
* **NFR-5**: Live bus data is retrieved and logged by the central system every 5 seconds.
* **NFR-6**: The live map should update within 5 seconds of the system receiving new bus data.
* **NFR-7**: Any historical data query should be fulfilled and the data supplied to the user within 10 seconds.