# Getting Started with Create React App

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

### `npm start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in your browser.

The page will reload when you make changes.\
You may also see any lint errors in the console.


## About 

Here we work with "Profiler" tab in react developers tools extansion and show how it works. 

`useMemo` caches the result of a function call and only calls the function again when its dependencies change.

* For checking component perfomance open "profiler" / "start record" make manipulations and "stop record" => look into graph

--

`React.memo()` is a higher-order component is a component that takes another component as an argument so that it can add functionality to it. In this case, React.memo() will only allow the component passed to it to re-render if its props have changed.

React will only shallowly compare the props of the memoized component before and after each render. To ensure that complex values such as objects and arrays are deeply compared, we can provide a comparison function as the second argument to `React.memo()`

* For checking wich component nead to be fixed open "profiler" / " ⚙ settings" / "✅ Highlight updates when components render." 


