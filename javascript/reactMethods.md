From [Scotch.io](https://scotch.io/tutorials/learning-react-getting-started-and-concepts)

**Lifecycle Methods**
- componentWillMount: Invoked once, on both client & server before rendering occurs.
- componentDidMount: Invoked once, only on the client, after rendering occurs.
- shouldComponentUpdate: Return value determines whether component should update.
- componentWillUnmount: Invoked prior to unmounting component.

**Specs**
- getInitialState: Return value is the initial value for state.
- getDefaultProps: Sets fallback props values if props aren’t supplied.
- mixins: An array of objects, used to extend the current component’s functionality.

**Const vs Class**
Const for generic componetn
Class for state that changes
