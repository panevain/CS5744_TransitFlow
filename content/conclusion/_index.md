+++
title = "Conclusion"

sort_by = "weight"
weight = 6
+++

This website has presented the use cases and requirements for a system which serves Blacksburg Transit bus and route information to riders through a variety of public interfaces. This system, named Reliaroute, is comprised of a server, administrative web app, database, and REST API.

The design presented aims to increase the reliability of information by taking advantage of the large amount of cacheable data. The back end makes use of a cache to decrease the resources required to serve massive numbers of clients and requests. The system also uses a three-layer design to separate the existing public interfaces from changes to the backend.