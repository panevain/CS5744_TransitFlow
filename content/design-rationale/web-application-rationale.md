+++
title = "Web Application"

sort_by = "weight"
weight = 3
+++

The one non-public interface is intended for system operators to create, read, update, and delete information which is served to public clients. Each of these operations can be accomplished by connecting to the database and writing SQL, but this is a high barrier to entry and risks damage to the data stored within. Each endpoint uses a DAO on the server-side to encapsulate the SQL operations being performed. Each endpoint can be triggered by a UI interaction, thereby reducing the complexity of interfacing with the system. 

The web app allows system operators to log in using their credentials. Their login credentials are then stored and passed with every request to an authenticated endpoint. This automation allows the administrative web app to use the same public endpoints as every other client while seamlessly accessing restricted endpoints too.

Benefits of Angular? @Andrew