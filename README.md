Question 4
We now wish to simulate the running of the entire road network. The simulation will involve cars entering the road network, proceeding through the network to their destination, and leaving the road network at different times. Write a function simulate(intersections, road_times, cars_to_add). Your function should track the position of each vehicle in the road network at each timestep, starting from timestep 0. Your function should return a list of actions specifying what each car currently in the road network is doing at each timestep. Valid actions are:

drive(timestep, car_id, source_node, destination_node) - This represents a car identified by car_id that is traversing the road between source_node and destination_node at timestep
wait(timestep, car_id, intersection_id) - This represents a car identified by car_id that is waiting at intersection intersection_id at timestep
arrive(timestep, car_id, destination) - This represents a car identified by car_id having arrived at destination at timestep
Each action should be represented as a string. The list of actions should be sorted first by timestep and then by car_id.

Your function should take the following arguments:
