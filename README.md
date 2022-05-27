Question 1
Write a function load_road_network(filename) that parses a file with the structure described below and returns a tuple containing two dictionaries.

The first dictionary should represent the intersections. The keys of this dictionary should be the ID numbers of each intersection and the values should be the corresponding list of traffic signals.

The second dictionary should represent the roads. The keys of this dictionary should be tuples containing the source and destination nodes of the road, and the values should be the number of timesteps required to traverse the corresponding road.

The structure of the file is as follows:

The text '#Intersection:' followed by the ID number (a positive integer or zero) of an intersecti


Question 2
A path through the road network can be described by listing each node the vehicle will travel through. For example, the path [2,0,4,6] would indicate that the vehicle starts at node 2, travels through nodes 0 and 4 then arrives at node 6. Recall that the first and last nodes must be location nodes, while all other nodes must be intersections. In this task we wish to understand:

Whether a vehicle starting its journey at timestep 0 is able to traverse the path without being stopped at any intersection, assuming there are no other vehicles on the road network
How long that journey would take
Write a function path_cost(path, intersections, road_times). If it is possible to traverse the path starting at timestep 0 without being stopped at any intersections then the function should return the total number of timesteps taken. If not, it should return None. You may assume that the path is a valid, traversable path.

Your function should take the following arguments:

Question 3
We now wish to consider a road network with multiple cars traversing it. In order to do that, we need to be able to identify which vehicles will be able to pass through a crowded intersection at any given time. We can represent each car currently waiting at an intersection by a tuple (car_id, path, arrival_time):

car_id is an integer that uniquely identifies a particular car.
path is a list representing the path that the car will take through the network.
arrival_time is an integer representing the timestep in which the car arrived at the intersection.
In this task, we will write a function to process a single step through time at a given intersection. Write a function intersection_step(intersections, road_times, intersection_id, cars_at_intersection, timestep). This function should return a list containing the car_id of each car that will be allowed to proceed through intersection intersection_id at the current timestep, sorted by car_id.




Question 4
We now wish to simulate the running of the entire road network. The simulation will involve cars entering the road network, proceeding through the network to their destination, and leaving the road network at different times. Write a function simulate(intersections, road_times, cars_to_add). Your function should track the position of each vehicle in the road network at each timestep, starting from timestep 0. Your function should return a list of actions specifying what each car currently in the road network is doing at each timestep. Valid actions are:

drive(timestep, car_id, source_node, destination_node) - This represents a car identified by car_id that is traversing the road between source_node and destination_node at timestep
wait(timestep, car_id, intersection_id) - This represents a car identified by car_id that is waiting at intersection intersection_id at timestep
arrive(timestep, car_id, destination) - This represents a car identified by car_id having arrived at destination at timestep
Each action should be represented as a string. The list of actions should be sorted first by timestep and then by car_id.

Your function should take the following arguments:


如果您需要任何关于此assignment的帮助，可以联系vx:codingtutor
