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


### Code Splitting Components 

`import DrivingDirectionsMap from './DrivingDirectionsMap';`

To split the DrivingDirectionsMap component into its own chunk, we can use 'React.lazy()', which has the following syntax:

```
const DrivingDirectionsMap = React.lazy(
  () => import('./DrivingDirections)
); 
```


### Suspense 

React load the rest of our app first, then insert our lazily loaded component, we can use the `<Suspense>` component from React.

The `<Suspense>` component instructs React to load every part of our app except the components imported with `React.lazy()`. While those components download, `<Suspense>` will show a loading state. Once the lazily loaded component is ready, `<Suspense>` will insert the component to our app.

``` 
<Suspense fallback={<p>Loading...</p>}>
  <p>some text</p>
</Suspense>
```
or insert a component as an argument of `fallback`
```
<Suspense fallback={<Loader/>}> 
  <p>some text</p>
</Suspense>
```
