# RSMP SXL for Sensors

## About
This document outlines what should go into a standardized RSMP SXL for Sensors. The document is work-in-progress, and will be expanded and structured as the working group continues discussions.

## Sensor Types
Theese sensor types are commonly used byt road authorities, and are supported initially:
- Inductive loops
- Radars
- Video sensor
- Push buttons
- Pneumatic Tubes

Less common use cases that we can consider later include:
- Gates (eg. RFID tags, number plates, etc)
- Lidar
- Magnometers
- Location of public transport (busses, trams). eg. IMPC, GPS, RFID, often via geofencing in a central system. more related to priority than to traffic data?

## Travel Time
Travel Time can be computed with eg:
- Automatic Number Plate Recognition
- WIFI/BLuetooth
- Video

Systems that deliver travel time should might be supported later.

### Data types
We focus on these data types:
- count (volume)
- speed
- presence (any vehicle/pedestrian present at the sensor at the moment?)
- occupancy (percent of time where someone was present at the sensor)
- density (percentage of road covered with vehicles. density of traffic)
 
Other data types to consider later:
- direction
- events - stopped vehicles, peoples behavior, dropped cargo, smoke...
- travel times
- ETA
- raw data
- meta data: quality/accuracy
- turn movements in intersections

## Classification
We need to support different national/EU schemes for classification.
Data should include the classification used.

### Aggregation
It should be possible to aggregate data by:
- time period
- classification

Perhaps we also need to consider aggregation by:
- detection zone

## Streaming data
RSMP does not currently provide a way to stream data that contain every single data point, except by sending every detection as a message, which is inefficient. we need a way to send package that contains a list of single data points (much like video or audio is commonly streamed).

Sending large amounts of data might require ways to prioritize message types in rsmp. For example if you want to send or stream a lot of traffic data.
