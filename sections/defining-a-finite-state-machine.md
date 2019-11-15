# Defining a finite state machine

*What is a finite state machine?*

A finite state machine has

- A finite number of events
- A finite number of states
- An `initial` state
- A set of final states
- A `transition` method that will determine the next state given the event and current state.

In our light bulb example had a finite set of states: lit, broken, unlit.

Build a state machine for our light bulb. 

Create our states and make a state object with them all.

```javascript
const lit = {}
const unlit = {}
const broken = {}

const states = {
  lit,
  unlit,
  broken
}
```

Now we've defined the nodes in our graph. We also need a way of describing events in our system. We can make `toggle` an event and our state will get an   `on` property, an object of event descriptors. 

```javascript
const unlit = {
  on: {
    TOGGLE: 'lit'
  }
}
```

We create our `lit` and `unlit` objects as ways of creating edges in our graph. 

When we have an event happen  we want to define a transition. On this, go here. 

Our `transition` method takes a state and event. if state config doesn’t exist we throw an error, we save the transition failure in case we fail. if state config doesn’t have our `ON` property that means it can’t handle the event that got passed in. if it has the `ON` property, we see if it has a transition. If transition doesn’t exist, return transition failure.

