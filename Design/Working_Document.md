# Car Traffic Simulator
## Working Document

###Problem Specification

The project of traffic simulation is to simulate the problems in the city which involve road, intersection and traffic 
light along with different vehicle types. This program is also to write a console based which will check and confirm 
classes and their functionality. This simulation will be able to simulate every  vehicle along with a single lane road,
interact with a traffic light. The final of this program is a GUI based program which can edit city and run simulation.

### User Stories

##### User Story - 1
Priority - Medium
As a user, I would like to see the current situation so that I could know the position of road shapes, traffic lights, 
and vehicles on the traffic.

##### User Story - 2
Priority - High
As a user, I want to be able to edit a city so that I can solve traffic lights and road shapes.

##### User Story - 3
Priority - Medium
As a user, I want to save the map where I can allocate roads and traffic lights so that I can easily
modify or reuse it to see how changes can affect or improve the traffic.

##### User Story - 4
Priority - High
As a user, I want to see how many vehicles and traffic lights are on the map and the average
speed of the vehicles so that I can understand how they can collectively affect road traffic
conditions and collisions.
### Decomposition
The problem can be strategically broken down into several simpler objects that are more manageable and understandable.
There are many objects, including, but not limited to:
#### Vehicle ####
It is the base class of Car, Bus, and Motorbike classes.  It has the following attributes:<br>
*vehicleID* - a unique identifier for every vehicle<br>
*speed* - speed of the vehicle.<br>
*length* - length of the vehicle.<br>
*currentRoad* - which road the vehicle is on currently.<br>
*startingCoordinate* - where the vehicle starts on the road.<br>
*finishingCoordinate* - where the vehicle ends on the road.<br>
*currentPosition* - the vehicle's current position on the road.<br>

The followings are the methods:<br>
*setRoad* - This method is used to place a vehicle on a desired road at the intersection.<br>
*moveForward* - The vehicle object can move forward by using this method.<br>

#### TrafficLight ####
This is the blueprint of traffic light objects in the program.  It has the following attributes:<br>
- *id* - a unique identifier that will differentiate each traffic light.
- *State* - the colour the ligth is displaying.
- *Position* - where the traffic light is located on the road.
- *Road attached to* - the road the light is attached to.

It has a method - updateCycle which update its status based on counter and timing.

#### Road ####
Road is one of the important classes in this program.  It has the following attributes:<br>
*roadID* - The identification of the road.<br>
*length* - How long the road is.<br>
*coordinateOne* - The coordinate of the first point.<br>
*coordinateTwo* - The coordinate of the second point.<br>
*trafficLightOne* - The traffic light object at one end.<br>
*trafficLightTwo* - The traffic light object at another end.<br>

#### Intersection ####
This class is the blue print of an intersection object where roads are met.
*intersectionPoint* - coordinate of where roads meet.<br>
*roads* - the list of roads that meet at the point.<br>

The followings are the methods:<br>
*addConnection* - This method will add a new road to the intersection.<br>
*validConnection* - This can check the connection has reached the maximum limit or not.<br>
*getRoad* - This method will give a random road from the intersection.<br>

#### City ####
This class associates with many other classes.  It has the following attributes:<br>
*roads* - list of roads that belongs to the city object.<br>
*intersections* - list of intersections that are in the city.<br>
*widthY* - the width of the city.<br>
*lengthX* - the length of the city.<br>

### Methods ###
Two modes: City and Simulation, will be included.
*To provide the user with roads and traffic lights.
*Randomly change the colour of the traffic lights.
*Statistics about the number of vehicles and traffic lights, the average speed of the
vehicles will be displayed.
*All vehicles will be moving along the lanes and decide if it is good to move depending
on the distance between the vehicles.
*Vehicles will disappear when they reach at the edges of the map.
*At intersection, vehicle randomly selects to go straight or turn.
