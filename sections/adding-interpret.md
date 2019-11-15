# Adding interpret

A machine is an abstract representation of a system. An *interpreter* brings it to life. An interpreter takes how the light bulb works and creates a service or an instance of your light bulb machine. 

we have our machine and interpreter, and we want to be able to create a service that interprets our bulb.

We can create a service that interprets our bulb. We also can send events that update our machine. 

```javascript
function interpret(machine) {
  let state = machine.initialState
  let isStarted = false

  const service = {
    currentState: () => state,
    send: (event) => {
      state = machine.transition(state, event)
    },
    start: () => {
      isStarted = true
      return service
    },
    stop: () => {
      isStarted = false
      return service
    }
  }

  return service
}
```

Our `send` event is simply updating the state to be our machine's transition event with the current state and the event passed in. 

Our `subscribe` method takes in a function and calls lur listeners. We store these in a set: ``` const listeners = new Set()```

