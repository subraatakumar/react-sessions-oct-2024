```html
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
    <style>
      body {
        font-family: Arial;
        margin: 0;
        padding: 0;
        background-color: #f4f4f4;
      }
      header {
        padding: 20px;
        text-align: center;
      }
      nav a {
        padding: 10px;
        color: #fff;
        text-decoration: none;
      }
      nav a:hover {
        background-color: #f4f4f4;
        color: #000;
        padding: 10px;
      }
      footer {
        text-align: center;
        padding: 10px;
      }
      .style1 {
        background-color: #333;
        color: #fff;
      }
    </style>
  </head>
  <body>
    <div id="root"></div>
    <script type="text/babel">
      const App = () => {
        const datas = [
          {
            userId: 1,
            id: 1,
            author: "Subrata",
            isLoggedIn: true,
            title:
              "sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
            body: "quia et suscipit\nsuscipit recusandae consequuntur expedita et cum\nreprehenderit molestiae ut ut quas totam\nnostrum rerum est autem sunt rem eveniet architecto",
          },
          {
            userId: 1,
            id: 2,
            author: "Ramesh",
            isLoggedIn: false,
            title: "qui est esse",
            body: "est rerum tempore vitae\nsequi sint nihil reprehenderit dolor beatae ea dolores neque\nfugiat blanditiis voluptate porro vel nihil molestiae ut reiciendis\nqui aperiam non debitis possimus qui neque nisi nulla",
          },
          {
            userId: 1,
            id: 3,
            title:
              "ea molestias quasi exercitationem repellat qui ipsa sit aut",
            body: "et iusto sed quo iure\nvoluptatem occaecati omnis eligendi aut ad\nvoluptatem doloribus vel accusantium quis pariatur\nmolestiae porro eius odio et labore et velit aut",
          },
          {
            userId: 1,
            id: 4,
            title: "eum et est occaecati",
            body: "ullam et saepe reiciendis voluptatem adipisci\nsit amet autem assumenda provident rerum culpa\nquis hic commodi nesciunt rem tenetur doloremque ipsam iure\nquis sunt voluptatem rerum illo velit",
          },
          {
            userId: 1,
            id: 5,
            title: "nesciunt quas odio",
            body: "repudiandae veniam quaerat sunt sed\nalias aut fugiat sit autem sed est\nvoluptatem omnis possimus esse voluptatibus quis\nest aut tenetur dolor neque",
          },
          {
            userId: 1,
            id: 6,
            title: "dolorem eum magni eos aperiam quia",
            body: "ut aspernatur corporis harum nihil quis provident sequi\nmollitia nobis aliquid molestiae\nperspiciatis et ea nemo ab reprehenderit accusantium quas\nvoluptate dolores velit et doloremque molestiae",
          },
        ];
        return (
          <>
            <HeaderFooterStyle>
              <Header />
            </HeaderFooterStyle>
            <BlogPostContainer datas={datas} />
            <HeaderFooterStyle>
              <Footer />
            </HeaderFooterStyle>
          </>
        );
      };

      const HeaderFooterStyle = ({ children }) => {
        return <div className="style1">{children}</div>;
      };

      const Header = () => {
        return (
          <header>
            <>
              <h1>Subrata's Blog</h1>
              <nav>
                <a href="#">Home</a>
                <a href="#">About</a>
                <a href="#">Contact</a>
              </nav>
            </>
          </header>
        );
      };

      const Footer = () => {
        return (
          <footer>
            <p>&copy; 2024 Subrata's Blog. All rights reserved.</p>
          </footer>
        );
      };

      const BlogPostContainer = ({ datas }) => {
        return (
          <>
            {datas.map((data) => (
              <BlogPost {...data} />
            ))}
          </>
        );
      };
      const BlogPost = ({ author, isLoggedIn, title, body }) => {
        return (
          <div
            style={{
              backgroundColor: "#fff",
              padding: 10,
              margin: 10,
              borderRadius: 10,
            }}
          >
            <h3>{title}</h3>
            {author && (
              <p
                style={{
                  color: "#FFF",
                  backgroundColor: "#666699",
                  border: "1px solid black",
                }}
              >
                {author}
                <span
                  style={{
                    paddingLeft: 10,
                    color: isLoggedIn ? "#66ff66" : "red",
                  }}
                >
                  {isLoggedIn ? "Avilable" : "NotAvailable"}
                </span>
                {
                  //  isLoggedIn ? (
                  //   <span style={{ paddingLeft: 10, color: "green" }}>
                  //     Available
                  //   </span>
                  // ) : (
                  //   <span style={{ paddingLeft: 10, color: "red" }}>
                  //     UnAvailable
                  //   </span>
                  // )
                }
              </p>
            )}
            <p>{body}</p>
          </div>
        );
      };

      const handleClick = () => {
        return true;
      };

      const root = ReactDOM.createRoot(document.getElementById("root"));
      root.render(<App />);
    </script>
  </body>
</html>
```

- Revised Code

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
    <style>
      body {
        font-family: Arial;
        margin: 0;
        padding: 0;
        background-color: #f4f4f4;
      }
      header {
        padding: 20px;
        text-align: center;
      }
      nav a {
        padding: 10px;
        color: #fff;
        text-decoration: none;
      }
      nav a:hover {
        background-color: #f4f4f4;
        color: #000;
        padding: 10px;
      }
      footer {
        text-align: center;
        padding: 10px;
      }
      .style1 {
        background-color: #333;
        color: #fff;
      }
    </style>
  </head>
  <body>
    <div id="root"></div>
    <script type="text/babel">
      const App = () => {
        const datas = [
          {
            userId: 1,
            id: 1,
            author: "Subrata",
            isLoggedIn: true,
            title:
              "sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
            body: "quia et suscipit\nsuscipit recusandae consequuntur expedita et cum\nreprehenderit molestiae ut ut quas totam\nnostrum rerum est autem sunt rem eveniet architecto",
          },
          {
            userId: 1,
            id: 2,
            author: "Ramesh",
            isLoggedIn: false,
            title: "qui est esse",
            body: "est rerum tempore vitae\nsequi sint nihil reprehenderit dolor beatae ea dolores neque\nfugiat blanditiis voluptate porro vel nihil molestiae ut reiciendis\nqui aperiam non debitis possimus qui neque nisi nulla",
          },
          {
            userId: 1,
            id: 3,
            title:
              "ea molestias quasi exercitationem repellat qui ipsa sit aut",
            body: "et iusto sed quo iure\nvoluptatem occaecati omnis eligendi aut ad\nvoluptatem doloribus vel accusantium quis pariatur\nmolestiae porro eius odio et labore et velit aut",
          },
          {
            userId: 1,
            id: 4,
            title: "eum et est occaecati",
            body: "ullam et saepe reiciendis voluptatem adipisci\nsit amet autem assumenda provident rerum culpa\nquis hic commodi nesciunt rem tenetur doloremque ipsam iure\nquis sunt voluptatem rerum illo velit",
          },
          {
            userId: 1,
            id: 5,
            title: "nesciunt quas odio",
            body: "repudiandae veniam quaerat sunt sed\nalias aut fugiat sit autem sed est\nvoluptatem omnis possimus esse voluptatibus quis\nest aut tenetur dolor neque",
          },
          {
            userId: 1,
            id: 6,
            author: "Bharath",
            isLoggedIn: true,
            title: "dolorem eum magni eos aperiam quia",
            body: "ut aspernatur corporis harum nihil quis provident sequi\nmollitia nobis aliquid molestiae\nperspiciatis et ea nemo ab reprehenderit accusantium quas\nvoluptate dolores velit et doloremque molestiae",
          },
        ];
        return (
          <>
            <HeaderFooterStyle>
              <Header />
            </HeaderFooterStyle>
            <BlogPostContainer datas={datas} />
            <HeaderFooterStyle>
              <Footer />
            </HeaderFooterStyle>
          </>
        );
      };

      const HeaderFooterStyle = ({ children }) => {
        return <div className={"style1"}>{children}</div>;
      };

      const Header = () => {
        return (
          <header>
            <>
              <h1>Subrata's Blog</h1>
              <nav>
                <a href="#">Home</a>
                <a href="#">About</a>
                <a href="#">Contact</a>
              </nav>
            </>
          </header>
        );
      };

      const Footer = () => {
        return (
          <footer>
            <p>&copy; 2024 Subrata's Blog. All rights reserved.</p>
          </footer>
        );
      };

      const BlogPostContainer = ({ datas }) => {
        return (
          <>
            {datas.map((data) => (
              <BlogPost {...data} />
            ))}
          </>
        );
      };
      const BlogPost = ({ author, isLoggedIn, title, body }) => {
        return (
          <div
            style={{
              backgroundColor: "#fff",
              padding: 10,
              margin: 10,
              borderRadius: 10,
            }}
          >
            <h3>{title}</h3>
            {author && <AuthorComp author={author} isLoggedIn={isLoggedIn} />}
            <p>{body}</p>
          </div>
        );
      };

      const handleClick = () => {
        return true;
      };

      const AuthorComp = ({ author, isLoggedIn }) => {
        return (
          <p
            style={{
              color: "#FFF",
              backgroundColor: "#666699",
              border: "1px solid black",
            }}
          >
            {author}
            <span
              style={{
                paddingLeft: 10,
                color: isLoggedIn ? "#66ff66" : "red",
              }}
            >
              {isLoggedIn ? "Avilable" : "NotAvailable"}
            </span>
            {
              //  isLoggedIn ? (
              //   <span style={{ paddingLeft: 10, color: "green" }}>
              //     Available
              //   </span>
              // ) : (
              //   <span style={{ paddingLeft: 10, color: "red" }}>
              //     UnAvailable
              //   </span>
              // )
            }
          </p>
        );
      };

      const root = ReactDOM.createRoot(document.getElementById("root"));
      root.render(<App />);
    </script>
  </body>
</html>
```
