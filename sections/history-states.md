# History states

A `history` state node returns the machine to the last state in that area of the machine (went transitioned to.)

Two kinds of history nodes:

- shallow - the default, returns the machine to the top level history value
- deep - updates all children states to their history value as well

History state can be useful in UI when we return a user to the state they were previously in.