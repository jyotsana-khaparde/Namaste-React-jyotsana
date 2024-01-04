## Q: What is `Code splitting` or `Chunking` or `Dynamic bundling` or `Lazy loading` or `On demand loading` or `Dynamic import`?

A: When we do logical seperation of the bundle that means a bundle should have enough code for a feaure and then we can split our bundle into the logical chunks so that you don't put load on a single bundle and the request for the js file does not become so heavy that it takes a lot of time to get into the browser. that is why we do code splitting.
Suppose there is a <Grocery> component or feature that we want to split form main bundle (in this case when our app will load initially it will not load the code for <Grocery> and only when we go to the grocery page then only <Grocery> code will load that's why it also called `lazy loading` where we are not loading evetthing we are loading lazy load when it required also know as `on demand loading`). then how to implement that?

- we won't import <Grocery> in the normal way we will load it by using `lazy()` this lazy comes form the `react` package. this lazy takes the callback function over there we import. this import is a function whoich takes the path of the <Grocery> component.
  eg:-
  - Old:- `import Grocery from "./components/grocery"`
  - New:- `const Grocery = lazy(() => import("./components/grocery))`
- when our app's bundle zise is increasing so to reduce the bundle size we do code splitting.

## Q: Why we got this `error`: A component was suspended while responding to `synchronous input`. This will cause the `UI` to be replaced with a `loading indicator`. To `fix this`, `updates that suspend` should be wrapped with `start transition`? How does `suspense fix` this error?

A: When we load the page initially we only get main bundle in network call and it does not have <Grocery> code in it. now we are loading the <Grocery> code on demand. that menas when we go to the grocery page then only the grocery bundle will load. the react throw the error meanwhile because the grocery bundle takes some time to load meanwhile react try to load the grocery component but the code was not there at that time that is why react suspends the rendering and throws the error.
to handle this react gives <Suspense> we can just wrap our React component with <Suspense> while doing lazy loading. and give the fallback (so fallback means what should be render untill the bundle is getting load. it can be any loading screen or shimmer loading)
eg:-
`<Suspense fallback={<Shimmer/>}>
    <Grocery />
</Suspense>`

## Q: `Advantages and Disadvantages` of using this `code splitting pattern`?

A:
`Advantages:-`

- Faster Initial Load Time: By splitting your code into smaller chunks and loading them on-demand, code splitting reduces the initial load time of your application.
- Improved Performance: With code splitting, you can optimize the performance of your React application by loading only the code that is needed for a particular page or user interaction. This reduces the amount of JavaScript that needs to be parsed and executed, leading to faster rendering and improved performance.
- Reduced Bandwidth Consumption: By loading only the necessary chunks, code splitting helps reduce the amount of data that needs to be downloaded. This is particularly beneficial for users on slow or limited internet connections, as it minimizes the bandwidth consumption and allows for a smoother browsing experience.
- Enhanced Caching and Resource Utilization: When using code splitting, chunks of your application can be cached individually. This means that if a user revisits your app or navigates to another page, the browser can use the cached chunks, reducing the need to download them again. Caching and efficient resource utilization contribute to improved performance and reduced server load.
  `Disadvantages:-`
- increased complexity in development and testing processes, more network requests that can affect performance, and additional code and dependencies that can increase the bundle size.

## Q: When do we and why do we need `suspense`?

A:
Suspense is a React feature that allows for components to be loaded asynchronously. It is used in conjunction with React.lazy. Suspense is also used to display a loading indicator while the component is being fetched, or it can be used to render a fallback component if the component fails to load. To use the Suspense component, we import it from the "react" package.

import { Suspense } from "react";

Next, we wrap a React.lazy loaded component inside it:

<Suspense>
    <LazyComponent />
</Suspense>

This will render the LazyComponent.

This is bad UX practice because the user will not know that a component will load. So we need to show the UX that something is coming, we will display a UI element to indicate to the user that a UI view will be loaded.

To do that in Suspense, we will use the fallback prop. Suspense uses the fallback prop to display a UI on the page while the lazily loaded component is still being loaded.

Let's add fallback to the above code, to display "Loading" before the LazyComponent is downloaded completely and rendered:

<Suspense fallback={"Loading..."}>
<LazyComponent />
</Suspense>

The fallback can take a JSX element:

<Suspense fallback={<div>Loading...</div>}>
<LazyComponent />
</Suspense>
