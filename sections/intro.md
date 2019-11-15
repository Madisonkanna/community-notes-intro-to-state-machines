# Intro

*What are states?*

Think of state as discriminate moments in a system in a particular place in time. In a world where state can’t change, you can imagine a lightbulb is always either lit or always *not* lit. 

```javascript
const alwaysLit = bulbFactory(true) 
const neverLit = bulbFactory(false) 
```

We often use booleans to change and update the state of our programs. Yet booleans can get complex quickly. 

- 1 boolean = 2 states
- 2 booleans = 4 states
- 3 booleans = 8 states

With booleans we can often end up in impossible states. In our `lightbulb` example we can end up with our light bulb broken and lit which is an impossible state. 

Is there a better way? What if we did not have state and things were just as they were? 

State represents a system at a particular point in time. If we use booleans we have 4 states but one of them is an impossible state.
So what if we wrote things in a way where that state wasn’t even an option?!

We can design our function so that it returns one of three states and will not get into an impossible state.

- `lit -> unlit`
- `unlit -> lit`
- `lit -> broken`
- `unlit -> broken`

This is our distinct set of states. This data structure is a directed graph. Our lightbult has 3 states: lit, unlit and broken. These states are represented as nodes, which means we can’t possibly be in 2 of them at the same time. 

We can't get into an impossible state as we can only go in two directions.  Our final state is broken, when the light bulb cannot transition away from this state. 

Instead of thinking of booleans on and off, think about what are the finite states/representations our systems can be in.




