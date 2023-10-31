+++
title = "Background"

sort_by = "weight"
weight = 1
+++

The Town of Blacksburg, Virginia is the home of Virginia Tech and its more than 37,000 students[^1]. Blacksburg's road and parking infrastructure is not designed to handle massive numbers of students driving to and from campus each school day. Simulatenously, many students may not own a car for personal or financial reasons. To make the area more accessible to all, the Town of Blacksburg offers daily bus service via Blacksburg Transit (BT), a system that connects student housing to the Virginia Tech campus and popular destinations in Blacksburg and Christiansburg. During a typical month when school is in session, BT serves approximately 400,000 riders across the entire network[^2].

{{ image(figure_number=1, 
citation_number=3, 
caption="BT bus 7021 turning onto Alumni Mall", 
src="./bt_bus.jpg", 
alt="BT bus 7021 turning right from North Main Street onto Alumni Mall")}}

BT experiences periods of surging demand, typically during the 15 minute periods when classes change due to students arriving to and departing from campus. This surge in user demand can cause the current BT mobile app and website to render all buses black and without route or capacity information, show buses in incorrect locations, or not show any buses at all. These periodic outages occur when most riders use the system, making it frustrating to plan a trip or catch a bus. 

{{ image(figure_number=2,
caption="A partial map outage as displayed in the iOS app", 
src="./bt_map_failure.png", 
alt="Blacksburg Transit iOS app showing black buses on an unloaded map"
narrow_image=true)}}

Each BT bus is equipped with a GPS and cellular transponder that provides each bus' location and status information. Each user, via website of mobile app, receives packets of JSON data which are displayed in tabular or graphical form. The system which exists between the buses supplying data and users consuming data is currently not able to handle the load and must, therefore, be redesigned to support users. TransitFlow is the replacement system which communicates with both parties. TransitFlow aims to solve these functionality problems while also providing new features to riders. The Town of Blacksburg, and more specifically Blacksburg Transit, are the customers for TransitFlow. The citizens of Blacksburg and Christiansburg as well as the Virginia Tech student body are the intended users of TransitFlow.

The remainder of this website explains its goals, requirements, design and rationale in detail.

[^1]: [VT University Data Commons](https://udc.vt.edu/irdata/data/students/enrollment/index) (Retrieved 11 October 2023)

[^2]: [Blacksburg Transit Monthly Ridership Reports](https://ridebt.org/images/reports/FY23_Reports/Monthly_Report_October_2022.pdf) (Retrieved 11 October 2023)

[^3]: [Virginia Department of Rail and Public Transportation](https://drpt.virginia.gov/wp-content/uploads/2023/05/Blacksburg-Transit-1024x683.jpg) (Retrieved 11 October 2023)