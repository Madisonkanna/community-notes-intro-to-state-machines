# Improving State Objects

To improve our state object we can return an object with a `value` property instead of a string. 

Create a helper function to allow states returned from `transition` back into the machine by handling when `transition` is handed an object or string for a state.

```javascript
//This is a curried function
const toStateObject = state =>
  typeof state === 'string' ? { value: state } : state
  ```

Use `toStateObject` at the top of the `transition` method. 

