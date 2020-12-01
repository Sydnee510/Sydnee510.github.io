---
layout: post
title:      "Redux --- mapDispatchToProps"
date:       2020-12-01 20:49:24 +0000
permalink:  redux_---_mapdispatchtoprops
---

Understanding the purpose of redux was very complex to understand. I went from building small components in react where each component had it's very own state, to handling state on a much global level with redux. Redux makes it very easy to share data accross all of your components. All you have to do to retrieve data from the global state is it subcribe or 'connect' to the redux store in the specific component where you need that data. 

To connect and retrieve data from the store, the data has to be fetched and then the action will need to be dispatched first... This is where both 'mapStateToProps' & 'mapDispatchToProps' comes into play.

`connect()` is a function that connects a React component to a Redux store. The function takes in multiple arguements with the first being` mapStateToProps` and the second being `mapDispatchToProps`
The only way to trigger a state change is by dispatching an action. With that being said, Actions are the only way to get data into the store. All data will eventually need to be dispatched to be accessible throughout all the components. 

Connect's signature function:
```
connect([mapStateToProps], [mapDispatchToProps], [mergeProps], [options])
```

By default, mapDispatchToProps is just dispatch => ({ dispatch }). So if you don't specify the second argument to connect(), you'll get dispatch injected as a prop in your component. mapDispatchToProps can either be an object, a function, or not supplied and It is used for dispatching actions to the store.

**EX. calling mapDispatchToProps as a function**
```
function mapStateToProps(state) {
  return { todos: state.todos }
}

function mapDispatchToProps(dispatch) {
  return { addTodo: bindActionCreators(addTodo, dispatch) }
}

export default connect(mapStateToProps, mapDispatchToProps)(Todos);
```

**EX. not calling mapDispatchToProps**
```
connect()(MyComponent)

connect(mapState)(MyComponent)

connect(mapState, null, mergeProps, options)(MyComponent)
```
