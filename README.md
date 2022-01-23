# Complete-React
# What is React
- React is a javascript library used for building interfaces.
- It handles the view layer of MVC model, neither controler nor model. It is just java script, not a templating language.
# Why React is Compelling
- It is Declarative and composable.
- It uses Virtual Dom.
- It allows one-way data binding to keep the comonents less conmplex.
- It is abstraction away from the DOM. (React help us to code away from the DOM, it lake care of handeling the dom with the help of virtualDOM).
- It re-renders the whole app on evry change[actually only chnaged part get modified].
- Mix and match components to build the UIs.
# React Fundamentals
- It has components.
- It does not have Models, ViewModels, Controllers, Directives, Global Evevnt Listners, Templates.
# Props and State
- Props are the data/variables that are getting passed from one component to other. These props can't be chnaged in child component.
- State are the data/variables that are used to store the information in the component. It gets changed over the component lifecycle.
# Lifecycle Mathods
- Every component follows a cycle since its creation to destruction, this cycle is called component lifecycle in Recat.
- Lifecycle is broadly categorized into 3 parts.
- Mounting.
- Updating.
- Unmounting
# Mounting
Mounting refers to creation of a component, it follows 4 sequential methods.
- constructor()
- getDerivedStatefromProps()
- render()
- componentDidMount()
ComponentWillMount is no more used.
# constructor()
- It is used to initialize the states.
- For binding the event handlers.
- Do not call setState() in this method
# render()
- This is only essential method in classbased components.
- This can return JSX, array, stringm number, Boolean, null etc.
- Render function is pure, means it returns the same props and state as given. Do not use setState() or Network call, or printing in screen.
# ComponentDidMount()
- It is called when ui get loaded in the screen.
- It is good to call API, setState(), set Timeout(), setInterval(), addEvevntListner, 
# Updating Phase
- This phase is responsible for upadtion on component/UI.
- It is called due to change is state or props.
- The methods that are getting called sequentially in this phase are, getDerivedStatefromProps(), shouldComponentUpdate(), render(), getSnapShotBeforUpdate(), componentDidUpdate().
- componetWillUpdate and componentWillgetProps() are no more used.
# getDerivedStateFromProps(props, state)
- It is called when componet recieves props for updating the state depending upon the props. It gets called once. It is called just befor render in both mounting and updatin state.
- This is very less used method.
# ShouldComponentUpdate(nextProps, nextState)
- To compare the previous props and state to update.
- It returns true by default.
- Better strategy is to use pureComponents.
# getSnapshopBeforUpdate()
- It gets called just before next render.
- It can be used for side-effects.
- It gives snapshot of DOM before updating the state.
# Unmounting phase
- it has only one function componentWillMount(), it gets called just before the component is removed from DOM.
- All cleanup things can be performed.
# Error Handeling through Error Boundries.
- Error boundries are React conponents having some predefined function associated to handle the errors.
- Only class based components have Error Voundries.
- Error boundaries can catch error in any lifecycle method. 
- getDerivedStateFromError() and componentDidCatch()
# static getDerivedStateFromError() 
- It does not allow side effect.
- It is called during the render method.
# componentDidCatch(error, info)
- We can use sideffect.
- It has error and information like which decendant component has error.

# React Hooks
- React hooks are the functions that allows to use state and lifecycle features.
- Hooks makes function component stateful from stateless.
- Hooks doesn't wprk in class based components.
# useState 
- it can't be used conditionaly.
- It should be declared at the top lavel.
# Effect Hook
- It allows to make sideeffect in the components.
- Side effects are Data Fetching, Setting up subscription, and manually changing the DOM is reffered as Side Effect.
- This is combination of conponentDidMount, conponentDidUpdate, componentWillUnmount.
- addEventListner is used inside the function, always make sure to cleanup everything.
- useEffect return the cleanup methods, where everything is cleanedup before the nextRender happens.
- useEffect is good fit to change the DOM, like title of the page, using 'window.title'.
- By default useEffect gets fired in all the re-renders(), but we can contraint it by passing second argument, as dependancy array.
- [a,b,c,d] meants any of the argument
# Effect as componentDidMount()
- useEffect(()=>{}, []) as we are passing an empty array that means useeffect wount not get fired on any changes in the component.
# Effect as componentDidUpdate()
- useEffect(()=>{}, [some value]) or useEffect(()=>{}) in this case useEffect get fired many times depending on changes in component, so it is working as componentDidMount and componentDidUpdate.
# Effect as componentWillUnmount()
- useEffect(()=>{ return function cleanup() }, []), when we keep something insde the cleanup it works as componentWillUnmount.

# useRef hook
- It is a hook whose value is fixed throughout the lifecycle of the Component.
- As name suggest it is helpful in getting the reference to a DOM element.
- const value = useRef(); // syntax for useref
- The object of useRef is not used directly, it is used as value.current.
# Debouncing
- It is helpful to constrain any task getting happened again and again, or making any function getting called after a specific time interval.
- It is not the function of React, but part of lodash.
# useReducer
- It is alternative of useState, so used for state management.
- It is preferable to use when complex state logic that involves multiple sub-value or when next state is dependent on previous state.
- It is helpful make the component more moduler, becaus estate management in seperated out from the Component.
- const [state, dispatch] = useReducer(updateState , {});
# useMemo
- It is react hook used for optimize the heavy functions. 
