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
        return (
          <>
            <HeaderFooterStyle>
              <Header />
            </HeaderFooterStyle>
            <BlogPost />
            <HeaderFooterStyle>
              <Footer />
            </HeaderFooterStyle>
          </>
        );
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

      const HeaderFooterStyle = ({ children }) => {
        return <div className="style1">{children}</div>;
      };

      const BlogPost = () => {
        return <div>post</div>;
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
