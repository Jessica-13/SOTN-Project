# SOTN-Project
This is a Netlogo project to explore the ways to place electric vehicle charging infrastructure in Dublin City area using agent-based modelling.

## Introduction
The purpose of this code is to modelize the placement of Electric vehicle charging stations around Dublin city centre and to come up with the optimal number of charging stations required. This code modelizes two types of charging stations namely, destination charging stations and enroute charging stations. As the model is based on Dublin city centre, the flow of Electric vehicles has been made around the popular destinations of the city centre and some grocery and general stores which tend to be visited by people more often. The agents i.e. the electric vehicles move around the map reaching different destinations and develop a preferential network of roads. This network of roads helps decide on the location of charging stations based on the popularity of the road. 

DCC has a vehicle charging strategy described in the 
<em> [Executive summary](https://www.dublincity.ie/residential/transportation/electric-vehicle-charging-information). </em>

This solution includes an agent-based model with maps and/or data for Dublin incorporated into the model.
The map that has been chosen is a section of Dublin city centre, obtained through Google Maps:

<p align="center">
<a href="https://user-images.githubusercontent.com/80853919/204019477-0a68c4b1-4432-4f26-bedc-2e4f9a9ecceb.png" target="_blank"><img src="https://user-images.githubusercontent.com/80853919/204019477-0a68c4b1-4432-4f26-bedc-2e4f9a9ecceb.png"  width="600"/></a>
</p>

The model consists of a feedback system that allows at the end of the simulation to obtain a suggestion of the most suitable position for the positioning of the electrical stations in the selected map.

### Interface

The model consists of a map to which are added a series of places of major interest and other specific points chosen as they are supposed to be subject to a greater influx of cars.

There are sliders that allow you to adjust some specifics of the cars, such as for example the viewing distance, which influences the choice of which road to take, as well as the number of tourists' cars and the number of delivery service cars.
In fact, the model includes two different types of agents, tourist cars are cars whose target are places of interest (the "commod destinaitons"), while delivery cars are cars that move faster towards random destinations.

It is also possible to change the number of electric charging stations that appear at the time of model setup (number fixed in this case at 200 since tests have shown that it represents a value consistent with the number of cars that are positioned at model setup, 50 + 50 cars).
One can also adjust the way roads become more or less popular, the level of full battery of cars as well as the level of "capacity" that is determined to be necessary in order to consider a station as necessary.

In the interface there are also monitors that allow to view:
- the number of cars that run out of battery and therefore fail to reach their target or a station in time ("count-dead-cars")
- the number of destinations that each car wants to reach and the ones that are actually reached ("count-destination-target", "count-destination-target-reached")
- the number of charging stations that cars want to reach and those that are actually reached ("count-station-target", "count-station-target-reached")

- a value that lets you know when the station selection will be made ("tick-count")
- ("dead-stations-one", "dead-stations-two" and "dead-stations-three") that show the decreae in the number of stations depending of their utility

In the model it is possible to observe the battery level of the cars which varies according to their movement as well as the number of customers of the stations which increases as the model is simulated.

### Code

The model informs about the suggested placement of the subset or the entirety of the necessary charging stations by showing the position of the stations really needed following a certain period of implementation of the code. 
In fact, the model includes a series of coordinates that refer to the major points of interest on the map as well as to other specific points on the map where a greater influx of cars is assumed. The agents then move around the map reaching the various destinations by developing a system of "preferential roads" which therefore become the most used ones and which therefore require a greater number of stations. 

After the first block in which all the agents and destinations are defined, global variables are defined which allow the data to be displayed via the monitors in the interface. Destinations are modeled by blue buildings, stations by crosses (at first green crosses represent in-route stations and orange crosses represent stations near destinations). Tourist cars are modeled in red and delivery service cars are modeled in yellow.

At first the stations are randomly placed (200 stations + 25 stations near the destinations).
Subsequently the number is decreased over time based on whether the stations are used or not. Only the most used stations remain until the end.
At the end of the simulation (tick-counter = 70000), only 8 stations that are really needed to serve a total of 100 cars.

<hr />

## Credits

<p align="center">
<a href="https://user-images.githubusercontent.com/80853919/204019277-1b5ee3a7-b744-478e-b49d-6c7ec6dfab01.jpg" target="_blank"><img src="https://user-images.githubusercontent.com/80853919/204019277-1b5ee3a7-b744-478e-b49d-6c7ec6dfab01.jpg"  width="350" /></a>
</p>

### Referent Professor
Siljak Harun

### Group members

Bury Lucas <br/>
Yang Weiyi <br/>
Porter Zachary <br/>
Sangem Priya Varenya <br/>
Spera Jessica <br/>
