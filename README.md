# DJS05 Project Brief: Building a Redux-Inspired Store for a Tally App

In this challenge, you will venture into the realm of state management by constructing a Redux-inspired store to manage the state of a simple Tally App. Your primary goal is to manage the app's state changes efficiently, focusing on core functionalities like incrementing, decrementing, and resetting a counter. Instead of rendering changes on the UI, you'll subscribe to state updates and log them to the console, highlighting the power of state management in applications.

## Objective
Create a minimalistic, Redux-inspired store to manage and log the state of a counting Tally App. Your implementation will not involve UI rendering; instead, it will use console logs to demonstrate state management effectively.

Observer Pattern resource from Refactoring Guru: https://refactoring.guru/design-patterns/observer

## User Stories (Gherkin Syntax)
Your challenge will encompass the following scenarios, tested through your store's implementation:

### SCENARIO 1: Initial State Verification
```
GIVEN no interactions have been performed yet
WHEN the “getState” method is run
AND the result is logged to the console
AND the browser console is open
THEN the state should show a count of 0
```

### SCENARIO 2: Incrementing the Counter
```
GIVEN no interactions have been performed yet
WHEN an “ADD” action is dispatched
AND another “ADD” action is dispatched
AND the browser console is open
THEN the state should show a count of 2
```

### SCENARIO 3: Decrementing the Counter
```
GIVEN the current count in the state is 2
WHEN a “SUBTRACT” action is dispatched
AND the browser console is open
THEN the state should display a count of 1
```

### SCENARIO 4: Resetting the Counter
```
GIVEN the current count in the state is 1
WHEN a “RESET” action is dispatched
AND the browser console is open
THEN the state should display a count of 0
```

## Tally App Redux-Inspired Store Documentation

## Overview

This project is designed to implement a Redux-inspired store for a Tally App. The primary focus is on state management, specifically managing state changes related to a simple counter. The core functionalities include incrementing, decrementing, and resetting the counter. This implementation does not involve any UI rendering. Instead, it uses console logs to demonstrate the effectiveness of state management.

## Objective

The main objective is to create a minimalistic store, inspired by Redux, to manage and log the state of a counting Tally App. The store should efficiently handle state changes and allow for the subscription to state updates, which are then logged to the console. This project aims to highlight the power of state management in applications.

## Key Features

1. **Global Store**: Implement a global store to hold the state of the tally counter.
2. **State Management Functions**: Develop functions to manage the state:
   - `getState`: Returns the current state.
   - `dispatch`: Takes an action and updates the state accordingly.
   - `subscribe`: Accepts a function that gets called whenever the state changes, logging the new state to the console.
3. **Functional Programming Principles**: Utilize functional programming concepts to structure the state management system.
4. **No UI Rendering**: Focus solely on state management without the complexity of UI rendering, making state changes observable through console logs.

## User Stories

### Scenario 1: Initial State Verification

**GIVEN** no interactions have been performed yet,  
**WHEN** the `getState` method is run and the result is logged to the console,  
**THEN** the state should show a count of 0.

### Scenario 2: Incrementing the Counter

**GIVEN** no interactions have been performed yet,  
**WHEN** an `ADD` action is dispatched and another `ADD` action is dispatched,  
**THEN** the state should show a count of 2.

### Scenario 3: Decrementing the Counter

**GIVEN** the current count in the state is 2,  
**WHEN** a `SUBTRACT` action is dispatched,  
**THEN** the state should display a count of 1.

### Scenario 4: Resetting the Counter

**GIVEN** the current count in the state is 1,  
**WHEN** a `RESET` action is dispatched,  
**THEN** the state should display a count of 0.

## Implementation Details

### Store Creation

The store is created using a `createStore` function, which takes a reducer function as its parameter. This function sets up the initial state, manages state updates through the dispatching of actions, and allows for the subscription to state changes.

#### `createStore` Function

The `createStore` function initializes the state and manages subscriptions. It holds the following core components:

1. **State Variable**: A variable to hold the current state of the store.
2. **Listeners Array**: An array to hold functions that will be called whenever the state changes.

The `createStore` function returns an object with methods to interact with the store:

- `getState`: Returns the current state.
- `dispatch`: Updates the state based on the provided action and notifies all subscribers.
- `subscribe`: Adds a new listener that gets called whenever the state changes.

### Reducer Function

The reducer function, named `counterReducer`, manages state updates for the counter. It takes the current state and an action as parameters and returns the next state based on the action type. The reducer handles three types of actions:

1. **ADD**: Increments the count by 1.
2. **SUBTRACT**: Decrements the count by 1.
3. **RESET**: Resets the count to 0.

If the action type is unknown, the reducer returns the current state without modification.

### Subscriptions and Event Handling

Subscribers can register callback functions to be notified of state changes. These functions are called whenever an action is dispatched, allowing the state to be logged to the console. This mechanism demonstrates the Observer pattern, where subscribers are notified of state changes.

Event listeners are attached to HTML buttons to dispatch actions when clicked. These buttons trigger the `ADD`, `SUBTRACT`, and `RESET` actions, allowing users to interact with the counter and observe state changes in the console.

## Functional Programming Principles

This implementation leverages functional programming principles to ensure a clean and maintainable codebase. Key principles applied include:

1. **Immutability**: The state is never modified directly. Instead, the reducer function returns a new state object based on the action type.
2. **Pure Functions**: The reducer function is a pure function, meaning it always returns the same output for a given input without causing side effects.
3. **First-Class Functions**: Functions are treated as first-class citizens, allowing them to be passed as arguments, returned from other functions, and assigned to variables.

## Testing the Implementation

To test the implementation, the following scenarios are covered:

1. **Initial State Verification**: Logging the initial state to verify that the count is 0.
2. **Incrementing the Counter**: Dispatching two `ADD` actions and logging the state to verify that the count is 2.
3. **Decrementing the Counter**: Dispatching a `SUBTRACT` action and logging the state to verify that the count is 1.
4. **Resetting the Counter**: Dispatching a `RESET` action and logging the state to verify that the count is 0.

These tests ensure that the store handles state changes correctly and that subscribers are notified of these changes.

## Challenges

### Understanding Redux Principles

Grasping the concepts of Redux, such as reducers, actions, and state management, was initially challenging. This required reviewing documentation and examples to understand how these principles work together to manage state effectively.

### Implementing the Subscribe Method

Ensuring that all subscribed listeners are called upon state changes required careful consideration. Testing and debugging helped ensure that the subscribe method worked as expected and that all listeners were notified of state changes.

### Managing State Updates

Updating the state in a way that adhered to immutability principles was crucial. The reducer function needed to return a new state object without modifying the existing state. This was achieved through careful implementation and testing.

