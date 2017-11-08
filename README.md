<img src="https://devmounta.in/img/logowhiteblue.png" width="250" align="right">

# Project Summary

In this project, we'll introduce you to React by creating a small project from scratch. We'll make use of the `create-react-app` CLI tool to quickly generate a React boilerplate. The goal of this project is to create a simple interface for creating a list of friends with their name and picture.

## Setup

* Fork and clone this repository.
* Run `sudo npm install -g create-react-app`.

## Step 1

### Summary

In this step, we'll use `create-react-app` to create a React boilerplate.

### Instructions

* `cd` into the root directory of the project.
* Run `create-react-app ./`.
* Delete the `README.md` the boilerplate generates and rename `README.old.md` back to `README.md`.

### Solution

<img src="https://github.com/DevMountain/react-1-mini/blob/solution/readme-assets/1g.gif" />

## Step 2

### Summary

In this step, we'll clear the boilerplate that is made for us in `src/App.js`.

### Instructions

* Open `src/App.js`.
* Inside of the `return()` statement, replace everything with a single `<div>` element.

### Solution

<details>

<summary> <code> src/App.js </code> </summary>

```js
import React, { Component } from 'react';
import logo from './logo.svg';
import './App.css';

class App extends Component {
  render() {
    return (
      <div>

      </div>
    );
  }
}

export default App;
```

</details>

## Step 3

### Summary

In this step, we'll add the necessary elements inside the `<div>` element for capturing user input.

### Instructions

* Open `src/App.js`.
* Inside of the `<div>` element add two inputs with lables and an `Add Friend` button:
  * The first input should be for getting a URL to a picture.
  * The second input should be for getting a name.
* Run `npm start` to spin up a development server and see your changes.

### Solution

<details>

<summary> <code> src/App.js </code> </summary>

```js
import React, { Component } from 'react';
import logo from './logo.svg';
import './App.css';

class App extends Component {
  render() {
    return (
      <div>
        <span>Picture:</span>
        <input />

        <span>Name:</span>
        <input />

        <button>Add Friend</button>
      </div>
    );
  }
}

export default App;
```

</details>

<br />

<img src="https://github.com/DevMountain/react-1-mini/blob/solution/readme-assets/1.png" />

## Step 4

### Summary

In this step, we'll add a `state` to our `src/App.js` for managing a list of friends and also the values for creating a new friend. 

### Instructions

* Open `src/App.js`.
* Above the `render` method, add a new method called `constructor`.
* Inside the `constructor` method, invoke `super`.
  * This allows us to set state.
* Create a new state object, by using `this.state = {}`, with the following keys:
  * `friends` - An empty array.
  * `picture` - An empty string.
  * `name` - An empty string.

### Solution

<details>

<summary> <code> src/App.js </code> </summary>

```js
import React, { Component } from 'react';
import logo from './logo.svg';
import './App.css';

class App extends Component {
  constructor() {
    super();

    this.state = {
      friends: [],
      picture: '',
      name: ''
    };
  }
  
  render() {
    return (
      <div>
        <span>Picture:</span>
        <input />

        <span>Name:</span>
        <input />

        <button>Add Friend</button>
      </div>
    );
  }
}

export default App;
```

</details>

## Step 5

In this step, we'll hook up our `input` elements to `state`. In order to do this, we'll need to create a custom method to update the value of `picture` and `name` on state. In React, you should never update state explicitly. You should always use the built-in method `this.setState()`.

### Instructions

* Open `src/App.js`.
* Underneath the `constructor` method, create a new method called `updateState`:
  * This method should have two parameters: `key` and `value`.
  * This methoud should call `this.setState` to update the given `key` with the given `value`.
    * Hint: Objects - Bracket Notation.
* On the first and second `input` elements, add an `onChange` property that captures the event and calls `this.updateState` with the correct key and the event's target value. Also add a `value` property that equals the correct key on `state`.


### Solution

<details>

<summary> <code> src/App.js </code> </summary>

```js
import React, { Component } from 'react';
import logo from './logo.svg';
import './App.css';

class App extends Component {
  constructor() {
    super();

    this.state = {
      friends: [],
      picture: '',
      name: ''
    };
  }

  updateState( key, value ) {
    this.setState({ [key]: value });
  }

  render() {
    return (
      <div>
        <span>Picture:</span>
        <input onChange={ ( e ) => this.updateState( 'picture', e.target.value ) } value={ this.state.picture } />

        <span>Name:</span>
        <input onChange={ ( e ) => this.updateState( 'name', e.target.value ) } value={ this.state.name } />

        <button>Add Friend</button>
      </div>
    );
  }
}

export default App;
```

</details>

<br />

<img src="https://github.com/DevMountain/react-1-mini/blob/solution/readme-assets/2g.gif" />

## Step 6

### Summary

In this step, we'll create method for adding a friend to the `friends` array on `state` and clear the values of `picture` and `name` on `state`.

### Instructions

## Contributions

If you see a problem or a typo, please fork, make the necessary changes, and create a pull request so we can review your changes and merge them into the master repo and branch.

## Copyright

© DevMountain LLC, 2017. Unauthorized use and/or duplication of this material without express and written permission from DevMountain, LLC is strictly prohibited. Excerpts and links may be used, provided that full and clear credit is given to DevMountain with appropriate and specific direction to the original content.

<p align="center">
<img src="https://devmounta.in/img/logowhiteblue.png" width="250">
</p>


