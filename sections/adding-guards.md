# Adding guards

Guards allow us to conditionally take a transition when we react to an event. 

`cond` property is a function that returns a boolean and recieves current `event` and `context`. This property is added to our transition object. Transition taken if `cond` returns `true.`

We can supply an array of transitions and take the first one that returns `true` from its `cond` function. 

Rename our const to `transitions` and use `toArray()`:

```const transitions = toArray(stateConfig.on[eventObject.type])```

Add a `for ..of` loop that returns early if a transition happens. 