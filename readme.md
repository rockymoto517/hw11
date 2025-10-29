### Challenges
[Extracting State Logic into a Reducer](extracting-state/readme.md) \
[Passing Data Deeply with Context](passing-data/readme.md) \

### Questions
a. State lifting is the concept of moving state variables towards parent components to share state with child components. Props drilling is the opposite concept, referring to how props are passed down several layers of components (that may not necessarily require the props) in order to be used by a component that requires it.

b. There are multiple ways to avoid props drilling. The first method is by using the special prop `children` in order to directly pass a prop to the component that requires it. If you find that you're passing props too deeply and you cannot cleanly pass to `children` directly, then the hook `useContext` may be used in order to manage complex states more cleanly.

c. `useState` will allow you to directly read/write to a variable in a snapshot while also allowing you to sequentially update stuff by using callback functions. `useReducer` takes a single 'reducer' function that will handle all possible types of 'actions' that are defined. In general, there's no particular reason to use `useState` over `useReducer` outside of personal preference, but there are some cases where one hook may be preferred. For example, in the case where you have many different event handlers that act similarly, then it may behoove you to put them inside of a `useReducer` hook, e.g. you need to write a form handler.

d. A re-render triggers in react every time the react *diff* algorithm finds a difference between the *render tree* built during the current snapshot and what is currently rendered. Some ways to affect the render tree are using the `set` funtion from `useState` or calling a `dispatch` function from `useReducer`. `useEffect` will also force a re-render every time it is called. In general, if you change a value in the state or call a function that *may or may not* change a value in the state, you will cause a re-render.
