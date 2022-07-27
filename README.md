# Getting Started with Create React App

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

### `npm start`

Open [http://localhost:3000](http://localhost:3000) to view it in your browser.


## About 

Here we work with "__Profiler__" tab in react developers tools extansion and show how it works. 

### Memoizing Values

`useMemo()` caches the result of a function call and only calls the function again when its dependencies change.

---
For checking component perfomance open "__profiler__" > "__start record__" make manipulations and "stop record" => look into the graph

---

### Memoizing Components

`React.memo()` is a higher-order component is a component that takes another component as an argument so that it can add functionality to it. In this case, React.memo() will only allow the component passed to it to re-render if its props have changed.

React will only shallowly compare the props of the memoized component before and after each render. To ensure that complex values such as objects and arrays are deeply compared, we can provide a comparison function as the second argument to `React.memo()`

---
For checking wich component nead to be fixed open "profiler" > " ⚙ settings" > "✅ Highlight updates when components render." 

---

### Memoizing Functions

`useCallback( ()=>{}, [] )` - hook will only recreate the function if its list of dependencies changes

### Code Splitting Modules 

Controll your `bundle.js`. Send the contents of the `moment` module when the user interacts with a feature that requires `moment` like in code: 
```
async function onClick() {
  const moment = await import('moment');
  setDate(moment.default(new Date()).format('MM/D/YYYY'))
}
```
---
Controll this in __chrome devtools__ > __Network__ (reload page and look in to `bundle.js` size)
