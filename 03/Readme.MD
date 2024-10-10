```js
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <script src="main.js"></script>
    <script
      src="https://unpkg.com/react@18/umd/react.development.js"
      crossorigin
    ></script>
    <script
      src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"
      crossorigin
    ></script>
    <script src="https://unpkg.com/@babel/standalone@7.8.3/babel.js"></script>
    <title>Document</title>
  </head>
  <body>
    <div id="root"></div>
    <script type="text/babel">
      const App = () => {
        return (
          <>
            <CounterComp />
          </>
        );
      };

      const CounterComp = () => {
        let counter = 1;

        const incCounter = () => {
          counter += 1;
        };

        const decCounter = () => {
          counter -= 1;
        };
        return (
          <div>
            <p>Counter : {counter}</p>
            <button onClick={incCounter}>Increase Counter</button>
            <button onClick={decCounter}>Decrease Counter</button>
          </div>
        );
      };

      const root = ReactDOM.createRoot(document.getElementById("root"));
      root.render(<App />);
    </script>
  </body>
</html>
```

- What is the issue in above code ?

