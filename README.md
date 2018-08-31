# react-syncing

Synchronize state between react components using pubsub.


## Instructions

If you extends from `Sync`: 

instead of using `setState`, use `set`,

instead of using `componentWillUnmount`, use `willUnmount`,

and instead of using `componentDidMount`, use `didMount`

That's all!

## Usage

```jsx
import Sync from "react-syncing";

export class App extends Sync {
  render(){
    return (<div>
      <p>{this.state.name}</p>
      <NameInput />
    </div>)
  }
}

```

From another component

```jsx
import Sync from "react-syncing";

export class NameInput extends Sync {
  didMount(){
    // Default name
    this.set({name: "Name"})
  }
  render(){
    return <input onInput={(e) => this.set({name: e.target.value})} />
  }
}
```