# Adding context

Certain systems can't be modeled with a finite state machine, such as text input. An input has infinite states.

Can store arbitrary infinite states (or extended state) on the `context` property of a machine.

`context` is an object on the machine that holds data to be passed to actions and functions. 

In our light bulb example we can use the `context` property to hold the current color value of the bulb. We can add a `CHANGE_COLOR` event to our states. 

Can ensure the target is set to the current state value even if our target is undefined with:

`const { target = value, actions = [] } = toTransitionObject(transition)`

`assign` is an action that updates the context of the given state. Assign can be given a function that returns an object or it can be given an object. Each key in the object signatre can be updated with a func that recieves `event`, `context`.

`machine.transition` must stay a pure function. We always want the same output. 

Machines can have a transition without a target. `changed` needs to make sure our `value` and `target` are not the same. 

Wire things together and update our interpreter to call actions with state context:

```javascript
state.actions.forEach(({ exec }) => {
  exec && exec(state.context, toEventObject(event))
})
```