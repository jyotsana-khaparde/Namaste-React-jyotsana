## Q: What is HOC (Higer Order Component)?
A: HOC is a function that takes the component as input and then it enchance that component it add some extra feature to the component and then returns the component back.
Eg:- 
`const withPromotedLabel = (ResturantCard) => {
  return (props) => {
    return (
      <>
        <label>
          Promoted
        </label>
        <ResturantCard {...props} />
      </>
    );
  };
};`

## Q: What is the Controlled and Uncontrolled component?
A: In React, Controlled components refer to the components where the state and behaviors are controlled by Parent components while Uncontrolled components are the ones having control of their own state and manage the behaviors on themselves.
Ex: If the component is getting hide and display based on it's own state then the component is uncontrolled component whereas if the component is getting hide and display based on it's parent component then the component is controlled component.

## Q: `Lifting state up` in react?
A: https://react.dev/learn/sharing-state-between-components 

## Q: What is `prop drilling` ?
A: Prop drilling occurs when a parent component generates its state and passes it down as props to its children components that do not consume the props – instead, they only pass it down to another component that finally consumes it.

## Q: How do you avoid prop drilling in React using Redux?
A: To avoid prop drilling, you can use techniques like React context or state management libraries (e.g., Redux, MobX) to make the data accessible to components deeper in the tree without manually passing props through all the intermediate components.

## Q: What is `context` in react?
A: Context, in React, is a powerful tool that allows us to share data between components without having to pass props down every level of a component tree.
Usually, you will pass information from a parent component to a child component via props. But passing props can become inconvenient if you have to pass them through many components in the middle, or if many components in your app need the same information. `Context` lets the parent component make some information available to any component in the tree below it—no matter how deep—without passing it explicitly through props.

1. We can create context using `createContext`, createContext is a function provided by `react` library.eg:-```const { createContext } = require("react");

const UserContext = createContext({
    loggedInUser: "Default User",
})

export default UserContext;```

2. Use `useContext` to access or use the context value in the function component. `useContext` is also hook provided by `react` library.
eg: ```const context = useContext(UserContext);```
3. Use `<UserContext.Consumer></UserContext.Consumer>` to access or use the context value in the class component. so when we creat a new context, react gives the power of `.Consumer` as well. inside `<UserContext.Consumer></UserContext.Consumer>` we can write JSX which has callback function and this callbcake function has access to the context value.
eg: ```<UserContext.Consumer>
            {(context) => <span>{context.loggedInUser}<span>}
       </UserContext.Consumer>```
4. Both these way (point 2 and 3) is to consume the context.
5. How to provide new value to the context? - The `.Provider` is responsible for updating and managing the context, which holds the data to be shared between components. so the context Provider is used to provide new value to the created context.
eg: ```<UserContext.Provider value={{ loggedInUser: userName }}>
        <Header />
        <Outlet />
        <Footer />
      </UserContext.Provider>```
All the components under the `</UserContext.Provider>` will have access of new context value. we can wrap whole components under the Provide or we can also wrap some portions of components whereever  we want to show new context value.

