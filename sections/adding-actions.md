# Adding actions

An action is a one-time side effect. An action can be defined on a transition. 

Add optional `actions` property on transition. When we have the `break` event in `lit` or `unlit` we fire an action as we transition to `broken.` 

Actions called always go in order (true of Xstate as well): 

1) current state's `exit`
2) transition actions
3) next state's `entry`

With `toActionObject` we noramlize our actions so each one is an object. 

