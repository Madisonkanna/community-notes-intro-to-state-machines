# Activites

*Activites* start when a state node is entered and stop when the node is exited. An activity is a function that recieves ```event``` and current ```context```. 

Activist should:

- Return a function that performs cleanup of functionality setup when the activity was started
- Only last during the duration of the state they were called in. 