- Using props in React Component

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
      const user1 = {
        name: "Subrata",
        desig: "Instructor",
        company: "Masai School",
      };

      const user2 = {
        name: "Ritesh",
        desig: "Instructor",
        company: "Masai School",
      };
      const handleClick = (e) => {
        console.log(e);
        alert("Button Clicked!");
      };

      const App = () => {
        return (
          <div>
            <Profile user={user1} />
            <Profile user={user2} />
          </div>
        );
      };
      const Profile = ({ user }) => {
        // Prop
        return (
          <div>
            <h1>{user.name}</h1>
            <p>{user.desig}</p>
            <p>{user.company}</p>
            <button onClick={(e) => handleClick(e)}>Click Me</button>
          </div>
        );
      };

      const root = ReactDOM.createRoot(document.getElementById("root"));
      root.render(<App />);
    </script>
  </body>
</html>
```

- destructing to get individual item as prop

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
      const user1 = {
        name: "Subrata",
        desig: "Instructor",
        company: "Masai School",
      };

      const user2 = {
        name: "Ritesh",
        desig: "Instructor",
        company: "Masai School",
      };
      const handleClick = (e) => {
        console.log(e);
        alert("Button Clicked!");
      };

      const App = () => {
        return (
          <div>
            <Profile
              name={user1.name}
              desig={user1.desig}
              company={user1.company}
            />
            <Profile
              name={user2.name}
              desig={user2.desig}
              company={user2.company}
            />
          </div>
        );
      };
      const Profile = ({ name, desig, company }) => {
        // Prop
        return (
          <div>
            <h1>{name}</h1>
            <p>{desig}</p>
            <p>{company}</p>
            <button onClick={(e) => handleClick(e)}>Click Me</button>
          </div>
        );
      };

      const root = ReactDOM.createRoot(document.getElementById("root"));
      root.render(<App />);
    </script>
  </body>
</html>
```
