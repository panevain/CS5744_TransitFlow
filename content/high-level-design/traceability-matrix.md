+++
title = "Traceability Matrix"

sort_by = "weight"
weight = 2
+++

You should also provide a **traceability matrix** that indicates how
individual requirements map to individual design components.

<style>
    .full-row {
        background-color: #eeeeee;
    }
    table {
        text-align: center;
        border-collapse: collapse;
    }
    th {
        padding: 0 10px;
        font-size: 15px;
    }
</style>

<table>
    <tr>
        <th>Requirement</th>
        <th>Web User Interface</th>
        <th>Mobile App Interface</th>
        <th>SMS Interface</th>
        <th>Internal Database</th>
        <th>Admin Web Interface</th>
        <th>Physical Collection Devices</th>
        <th>REST API Controllers</th>
        <th>REST API Services</th>
        <th>Caching Services</th>
    </tr>
    <tr>
        <td colspan="11" class="full-row">Functional Requirements</td>
    </tr>
    <tr>
        <!-- FR-1: Users can view live bus locations on a map. -->
        <td><strong>FR-1</strong></td>
        <td>X</td> <!-- Web User Interface -->
        <td>X</td> <!-- Mobile App Interface -->
        <td> </td> <!-- SMS Interface -->
        <td>X</td> <!-- Internal Database -->
        <td> </td> <!-- Admin Web Interface -->
        <td> </td> <!-- Physical Collection Devices -->
        <td>X</td> <!-- REST API Controllers -->
        <td>X</td> <!-- REST API Services -->
        <td>X</td> <!-- Caching Services -->
    </tr>
    <tr>
        <!-- FR-2: Users can view live ridership information per bus. -->
        <td><strong>FR-2</strong></td>
        <td>X</td> <!-- Web User Interface -->
        <td>X</td> <!-- Mobile App Interface -->
        <td> </td> <!-- SMS Interface -->
        <td>X</td> <!-- Internal Database -->
        <td> </td> <!-- Admin Web Interface -->
        <td> </td> <!-- Physical Collection Devices -->
        <td>X</td> <!-- REST API Controllers -->
        <td>X</td> <!-- REST API Services -->
        <td>X</td> <!-- Caching Services -->
    </tr>
    <tr>
        <!-- FR-3: Users can receive route and detour information. -->
        <td><strong>FR-3</strong></td>
        <td>X</td> <!-- Web User Interface -->
        <td>X</td> <!-- Mobile App Interface -->
        <td> </td> <!-- SMS Interface -->
        <td>X</td> <!-- Internal Database -->
        <td> </td> <!-- Admin Web Interface -->
        <td> </td> <!-- Physical Collection Devices -->
        <td>X</td> <!-- REST API Controllers -->
        <td>X</td> <!-- REST API Services -->
        <!-- TODO: Are we going to be caching on all endpoints? -->
        <td>X</td> <!-- Caching Services -->
    </tr>
    <tr>
        <!-- FR-4: Users can select a route to view that route on the map, or view all of the routes on the map. -->
        <td><strong>FR-4</strong></td>
        <td>X</td> <!-- Web User Interface -->
        <td>X</td> <!-- Mobile App Interface -->
        <td> </td> <!-- SMS Interface -->
        <td>X</td> <!-- Internal Database -->
        <td> </td> <!-- Admin Web Interface -->
        <td> </td> <!-- Physical Collection Devices -->
        <td>X</td> <!-- REST API Controllers -->
        <td>X</td> <!-- REST API Services -->
        <td>X</td> <!-- Caching Services -->
    </tr>
    <tr>
        <!-- FR-5: Users can view a list all routes in text format. -->
        <td><strong>FR-5</strong></td>
        <td>X</td> <!-- Web User Interface -->
        <td>X</td> <!-- Mobile App Interface -->
        <td>X</td> <!-- SMS Interface -->
        <td>X</td> <!-- Internal Database -->
        <td> </td> <!-- Admin Web Interface -->
        <td> </td> <!-- Physical Collection Devices -->
        <td>X</td> <!-- REST API Controllers -->
        <td>X</td> <!-- REST API Services -->
        <td>X</td> <!-- Caching Services -->
    </tr>
    <tr>
        <!-- FR-6: Users can view a list of all routes that service a stop. -->
        <td><strong>FR-6</strong></td>
        <td>X</td> <!-- Web User Interface -->
        <td>X</td> <!-- Mobile App Interface -->
        <td>X</td> <!-- SMS Interface -->
        <td>X</td> <!-- Internal Database -->
        <td> </td> <!-- Admin Web Interface -->
        <td> </td> <!-- Physical Collection Devices -->
        <td>X</td> <!-- REST API Controllers -->
        <td>X</td> <!-- REST API Services -->
        <td>X</td> <!-- Caching Services -->
    </tr>
    <tr>
        <!-- FR-7: Users can view a list of all buses that service a particular
        stop and the estimated time that those buses will arrive at the stop. -->
        <td><strong>FR-7</strong></td>
        <td>X</td> <!-- Web User Interface -->
        <td>X</td> <!-- Mobile App Interface -->
        <td>X</td> <!-- SMS Interface -->
        <td>X</td> <!-- Internal Database -->
        <td> </td> <!-- Admin Web Interface -->
        <td> </td> <!-- Physical Collection Devices -->
        <td>X</td> <!-- REST API Controllers -->
        <td>X</td> <!-- REST API Services -->
        <td>X</td> <!-- Caching Services -->
    </tr>
    <tr>
        <!-- FR-8: Users can view all alerts in the system. -->
        <td><strong>FR-8</strong></td>
        <td>X</td> <!-- Web User Interface -->
        <td>X</td> <!-- Mobile App Interface -->
        <td>X</td> <!-- SMS Interface -->
        <td>X</td> <!-- Internal Database -->
        <td> </td> <!-- Admin Web Interface -->
        <td> </td> <!-- Physical Collection Devices -->
        <td>X</td> <!-- REST API Controllers -->
        <td>X</td> <!-- REST API Services -->
        <td>X</td> <!-- Caching Services -->
    </tr>
    <tr>
        <!-- FR-9: Users can do all of the above actions either through a web or mobile application. -->
        <td><strong>FR-9</strong></td>
        <td>X</td> <!-- Web User Interface -->
        <td>X</td> <!-- Mobile App Interface -->
        <td> </td> <!-- SMS Interface -->
        <td>X</td> <!-- Internal Database -->
        <td> </td> <!-- Admin Web Interface -->
        <td> </td> <!-- Physical Collection Devices -->
        <td>X</td> <!-- REST API Controllers -->
        <td>X</td> <!-- REST API Services -->
        <td>X</td> <!-- Caching Services -->
    </tr>
    <tr>
        <!-- FR-10: Users can accomplish FR-6, FR-7, and FR-8 via text. -->
        <td><strong>FR-10</strong></td>
        <td>X</td> <!-- Web User Interface -->
        <td>X</td> <!-- Mobile App Interface -->
        <td>X</td> <!-- SMS Interface -->
        <td>X</td> <!-- Internal Database -->
        <td> </td> <!-- Admin Web Interface -->
        <td> </td> <!-- Physical Collection Devices -->
        <td>X</td> <!-- REST API Controllers -->
        <td>X</td> <!-- REST API Services -->
        <td>X</td> <!-- Caching Services -->
    </tr>
    <tr>
        <!-- FR-11: Users can access historical bus and ridership information. -->
        <td><strong>FR-11</strong></td>
        <td>X</td> <!-- Web User Interface -->
        <td>X</td> <!-- Mobile App Interface -->
        <td> </td> <!-- SMS Interface -->
        <td>X</td> <!-- Internal Database -->
        <td> </td> <!-- Admin Web Interface -->
        <td> </td> <!-- Physical Collection Devices -->
        <td>X</td> <!-- REST API Controllers -->
        <td>X</td> <!-- REST API Services -->
        <td>X</td> <!-- Caching Services -->
    </tr>
    <tr>
        <!-- FR-12: Administrative users can enter, modify, and delete bus information. -->
        <td><strong>FR-12</strong></td>
        <td> </td> <!-- Web User Interface -->
        <td> </td> <!-- Mobile App Interface -->
        <td> </td> <!-- SMS Interface -->
        <td>X</td> <!-- Internal Database -->
        <td>X</td> <!-- Admin Web Interface -->
        <td> </td> <!-- Physical Collection Devices -->
        <td>X</td> <!-- REST API Controllers -->
        <td>X</td> <!-- REST API Services -->
        <td> </td> <!-- Caching Services -->
    </tr>
    <tr>
        <!-- FR-13: Administrative users can enter, modify, and delete route information and route stops. -->
        <td><strong>FR-13</strong></td>
        <td> </td> <!-- Web User Interface -->
        <td> </td> <!-- Mobile App Interface -->
        <td> </td> <!-- SMS Interface -->
        <td>X</td> <!-- Internal Database -->
        <td>X</td> <!-- Admin Web Interface -->
        <td> </td> <!-- Physical Collection Devices -->
        <td>X</td> <!-- REST API Controllers -->
        <td>X</td> <!-- REST API Services -->
        <td> </td> <!-- Caching Services -->
    </tr>
    <tr>
        <!-- FR-14: Administrative users can enter, modify, and delete alerts. -->
        <td><strong>FR-14</strong></td>
        <td> </td> <!-- Web User Interface -->
        <td> </td> <!-- Mobile App Interface -->
        <td> </td> <!-- SMS Interface -->
        <td>X</td> <!-- Internal Database -->
        <td>X</td> <!-- Admin Web Interface -->
        <td> </td> <!-- Physical Collection Devices -->
        <td>X</td> <!-- REST API Controllers -->
        <td>X</td> <!-- REST API Services -->
        <td> </td> <!-- Caching Services -->
    </tr>
    <tr>
        <!-- FR-15: The system logs all bus location and status information in a centralized database. -->
        <td><strong>FR-15</strong></td>
        <td> </td> <!-- Web User Interface -->
        <td> </td> <!-- Mobile App Interface -->
        <td> </td> <!-- SMS Interface -->
        <td>X</td> <!-- Internal Database -->
        <td> </td> <!-- Admin Web Interface -->
        <td>X</td> <!-- Physical Collection Devices -->
        <td>X</td> <!-- REST API Controllers -->
        <td>X</td> <!-- REST API Services -->
        <td> </td> <!-- Caching Services -->
    </tr>
    <tr>
        <td colspan="11" class="full-row">Non-Functional Requirements</td>
    </tr>
    <tr>
        <!-- NFR-1: The application should be available and able return data to users 99.99% of the time. -->
        <!-- TODO: Are all components required to deliver data regardless of the medium (web, mobile, sms)? -->
        <td><strong>NFR-1</strong></td>
        <td>X</td> <!-- Web User Interface -->
        <td>X</td> <!-- Mobile App Interface -->
        <td>X</td> <!-- SMS Interface -->
        <td>X</td> <!-- Internal Database -->
        <td>X</td> <!-- Admin Web Interface -->
        <td>X</td> <!-- Physical Collection Devices -->
        <td>X</td> <!-- REST API Controllers -->
        <td>X</td> <!-- REST API Services -->
        <td>X</td> <!-- Caching Services -->
    </tr>
    <tr>
        <!-- NFR-2: The application should always be available during peak times (approximately 8am to 4 pm). -->
        <td><strong>NFR-2</strong></td>
        <td> </td> <!-- Web User Interface -->
        <td> </td> <!-- Mobile App Interface -->
        <td> </td> <!-- SMS Interface -->
        <td> </td> <!-- Internal Database -->
        <td>X</td> <!-- Admin Web Interface -->
        <td> </td> <!-- Physical Collection Devices -->
        <td> </td> <!-- REST API Controllers -->
        <td> </td> <!-- REST API Services -->
        <td> </td> <!-- Caching Services -->
    </tr>
    <tr>
        <!-- NFR-3: The application should automatically scale to support approximately 10 thousand users during peak load. -->
        <td><strong>NFR-3</strong></td>
        <td> </td> <!-- Web User Interface -->
        <td> </td> <!-- Mobile App Interface -->
        <td> </td> <!-- SMS Interface -->
        <td> </td> <!-- Internal Database -->
        <td>X</td> <!-- Admin Web Interface -->
        <td> </td> <!-- Physical Collection Devices -->
        <td> </td> <!-- REST API Controllers -->
        <td> </td> <!-- REST API Services -->
        <td> </td> <!-- Caching Services -->
    </tr>
    <tr>
        <!-- NFR-4: The application, be it the web application or mobile application, should load the live map within 2 seconds. -->
        <td><strong>NFR-4</strong></td>
        <td>X</td> <!-- Web User Interface -->
        <td>X</td> <!-- Mobile App Interface -->
        <td> </td> <!-- SMS Interface -->
        <td> </td> <!-- Internal Database -->
        <td> </td> <!-- Admin Web Interface -->
        <td> </td> <!-- Physical Collection Devices -->
        <td> </td> <!-- REST API Controllers -->
        <td> </td> <!-- REST API Services -->
        <td> </td> <!-- Caching Services -->
    </tr>
    <tr>
        <!-- NFR-5: Live bus data is retrieved and logged by the central system every 4 seconds. -->
        <td><strong>NFR-5</strong></td>
        <td>X</td> <!-- Web User Interface -->
        <td>X</td> <!-- Mobile App Interface -->
        <td> </td> <!-- SMS Interface -->
        <td>X</td> <!-- Internal Database -->
        <td> </td> <!-- Admin Web Interface -->
        <td> </td> <!-- Physical Collection Devices -->
        <td>X</td> <!-- REST API Controllers -->
        <td>X</td> <!-- REST API Services -->
        <td>X</td> <!-- Caching Services -->
    </tr>
    <tr>
        <!-- NFR-6: The live map should update within 4 seconds of the system receiving new bus data. -->
        <td><strong>NFR-6</strong></td>
        <td>X</td> <!-- Web User Interface -->
        <td>X</td> <!-- Mobile App Interface -->
        <td> </td> <!-- SMS Interface -->
        <td> </td> <!-- Internal Database -->
        <td> </td> <!-- Admin Web Interface -->
        <td> </td> <!-- Physical Collection Devices -->
        <td> </td> <!-- REST API Controllers -->
        <td> </td> <!-- REST API Services -->
        <td> </td> <!-- Caching Services -->
    </tr>
    <tr>
        <!-- NFR-7: Any historical data query should be fulfilled and the data supplied to the user within 10 seconds. -->
        <td><strong>NFR-7</strong></td>
        <td>X</td> <!-- Web User Interface -->
        <td>X</td> <!-- Mobile App Interface -->
        <td> </td> <!-- SMS Interface -->
        <td>X</td> <!-- Internal Database -->
        <td> </td> <!-- Admin Web Interface -->
        <td> </td> <!-- Physical Collection Devices -->
        <td>X</td> <!-- REST API Controllers -->
        <td>X</td> <!-- REST API Services -->
        <td>X</td> <!-- Caching Services -->
    </tr>
</table>
