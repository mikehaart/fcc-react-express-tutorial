Super simple API tutorial using React and Express [FCC Link](https://www.freecodecamp.org/news/how-to-create-a-react-app-with-a-node-backend-the-complete-guide/)

### What's going on?
#### Server-side
Server folder contains the Express server.

```js
app.get("/api", (req, res) => {
    res.json({ message: "Hello from server!" });
});
```
#### Front-end
Inside `package.json` we set `"proxy": "http://localhost:3001"` so that we don't have to provide the origin that the server is running on each time we send a query. [React proxy docs](https://create-react-app.dev/docs/proxying-api-requests-in-development/).

Inside the `App.js` component we use react's `UseEffect()` hook to call `fetch()` that hits our Express back-end. Because the `fetch()` call is async we can use the `then()` method to handle the incoming JSON, and store the value of the 'message' property into the `data` state hook.

Because we now have the data stored in the state, we can display it on the page using a ternary operator in the returned jsx markup. 🥳
