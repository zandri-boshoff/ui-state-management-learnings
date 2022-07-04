# ui-state-management-learnings

## Redux

- Redux is a third party React library.
- Redux is a state management system for cross-component or app wide state.
- Different states consist of:

1. Local State
   1. State that belongs to a single component
   2. Can manage state with useState hook
2. Cross Component State
   1. State that affects multiple components
   2. Requires prop chains
3. App wide state
   1. State that affects the entire app ( most or all components ) for example user authentication status

- Redux or React Context can be used to manage cross component state as well as app wide state.

## How does Redux work?

- Redux has 1 store for all state in the entire application.
- A component will never directly change the state of the redux store.
  1. A component will dispatch an action.
  2. The action will be forwarder to the reducer.
  3. The reducer will then mutate (change) the store's data.
  4. After creating the store it needs to be exported and provided to the main react app. All components inside of the main react app can then subscribe to the data inside of the store and also dispatch actions.

### The Reducer Function

- This should be a pure function ( some input leads to some output - no side effects like api calls ).
- The reducer has 2 input parameters ( old state - receives by default because the library executes the reducer, dispatched action )
- The output of the reducer function is a new state object.
- The reducer should be passed to the store, because the store needs to know which reducer is responsible for changing the store.
- When running your app for the first time the reducer function will run. The problem is the initial state is null so the reducer function will bomb out. Therefore the initial state should be given a default value.

### The Action

- An action is a JS object containing 2 properties namely a type (string) and the data.
- Different actions are forwarded to different reducers so different things will be done to the state.
- Dispatch is a method that sends an action.

### Connecting components to the store

-

## Sources

- Maximillian Swarchmuller
