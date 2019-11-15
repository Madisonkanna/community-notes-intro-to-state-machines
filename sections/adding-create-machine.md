# Adding `createMachine`

We need a function that takes our config and does something. We create a `createFactory` function that accepts our config. It should compute the next given state and the event. 

`transition` is a pure function that gets a state and decides the next state.

