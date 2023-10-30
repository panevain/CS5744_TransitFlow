+++
title = "Architecture"

sort_by = "weight"
weight = 1
+++

TransitFlow is organized into a three layer architecture.

## Presentation Layer
The separation between the presentation layer and the rest of the system allows for the reuse of the existing public interfaces. The changes to any particular interface can be implemented without changing any of the lower layer. Because BT is a public service, its data is made [publicly available](https://public.resource.org/8_principles.html). The non-authenticated REST API allows any member of the public to make their own interface using TransitFlow-supplied data.

## Application Layer

A vast majority of the transaction with the application layer are public clients requesting state information about buses, routes, and patterns. This information is inherently cacheable which has two major benefits: the processing power required to generate the responses to client requests is fixed and the time to respond to a client is minimized. 

The maximum number of expected requests can currently be handled with a simple key-value store. In the future, it would be relatively simple to use a standalone cache on a separate machine like [Redis](https://redis.io/) if user demand requires it.

The number of buses is relatively small and the frequency of data updates allows all of the data processing to occur on one machine. Running TransitFlow locally reduces the round-trip latency to clients accessing the system from Blacksburg.

Many clients use HTTP to make requests, but TransitFlow must also support SMS clients. The use of an external service like Twilio reduces the system's complexity while allowing TransitFlow to exclusively deal with HTTP requests.

## Data Layer

The use of a relational database allows current and historical information to be easily searched using SQL. MySQL is a performant and reliable RDBMS which is well suited to the volume of data being generated and managed. MySQL offers [full, physical backups](https://dev.mysql.com/doc/mysql-backup-excerpt/8.2/en/backup-and-recovery.html) which increases the resilience of the system. Backups can be triggered with a CRON-like interface and stored on an other machine offsite.

