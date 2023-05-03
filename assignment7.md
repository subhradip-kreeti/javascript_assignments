# 1.Write a JavaScript program that adds a new item to the list whenever a user inputs a text into the input field and clicks the button.

```javascript
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <style>
      * {
        font-size: 1.5rem;
      }
    </style>
  </head>
  <body>
    <ul id="my-list">
      <li>Dish 1</li>
      <li>Dish 2</li>
      <li>Dish 3</li>
      <li>Dish 4</li>
    </ul>

    <label for="entry">Enter New item</label>
    <input type="text" id="entry" />
    <button onclick="addItem()">Add Dish</button>

    <script>
      function addItem() {
        item = document.getElementById('entry').value;
        list = document.getElementById('my-list');
        listItem = document.createElement('li');
        listItem.appendChild(document.createTextNode(item));
        list.appendChild(listItem);
      }
    </script>
  </body>
</html>

```

# 2.Write a JS function to change the font size,bg-color, and font-family for the paragraph in the HTML snippet below on clicking the button.

```javascript
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>JS DOM paragraph styling</title>
  </head>
  <body>
    <p id="text">
      It is a long established fact that a reader will be distracted by the
      readable content of a page when looking at its layout.
    </p>
    <div>
      <button id="jsstyle" onclick="fun()">Style</button>
    </div>

    <script>
      function fun() {
        var styles = {
        "background-color": "lightgray",
        "font-family": "sans-serif",
        "font-size": "1.5rem",
      };

      var obj = document.getElementById("text");
      Object.assign(obj.style, styles);
      }
    </script>
  </body>
</html>

```

# 3.Write a JavaScript program that calculates the area of a rectangle when the user inputs the width and height into two input fields and clicks a button.

```javascript
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body>
    <h3>Enter width and height of a rectangle amd get it's Area</h3>
    <div id="inputs">
      <label for="width">Width</label>
      <input type="number" id="width" />

      <label for="height">Height</label>
      <input type="number" id="height" />

      <button onclick="calculateArea()">Calculate</button>
      <br />
      <h4 >Area of the rectangle is : <span id="result"></span> </h4>
    </div>

    <script>
      function calculateArea() {
        width = document.getElementById("width").value;
        height = document.getElementById("height").value;
        width = Number(width);
        height = Number(height);
        ans = width*height;
        document.getElementById("result").innerHTML=ans.toString();
      }
    </script>
  </body>
</html>

```

# 4.Write a JavaScript program that displays an alert message to the user when they submit a form.

```javascript
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />

    <link
      href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css"
      rel="stylesheet"
      integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC"
      crossorigin="anonymous" />

    <title>Hello, world!</title>
  </head>
  <body>
    <div class="container">
      <form>
        <div class="mb-3">
          <label for="exampleInputEmail1" class="form-label">
            Email address
          </label>
          <input
            type="email"
            class="form-control"
            id="exampleInputEmail1"
            aria-describedby="emailHelp" />
          <div id="emailHelp" class="form-text">
            We'll never share your email with anyone else.
          </div>
        </div>
        <div class="mb-3">
          <label for="exampleInputPassword1" class="form-label">Password</label>
          <input
            type="password"
            class="form-control"
            id="exampleInputPassword1" />
        </div>
        <div class="mb-3 form-check">
          <input type="checkbox" class="form-check-input" id="exampleCheck1" />
          <label class="form-check-label" for="exampleCheck1">
            Check me out
          </label>
        </div>
        <button type="submit" class="btn btn-primary" onclick="fun()">
          Submit
        </button>
      </form>
    </div>
    <script>
      function fun() {
        window.alert("its' a demo alert");
      }
    </script>
    <script
      src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/js/bootstrap.bundle.min.js"
      integrity="sha384-MrcW6ZMFYlzcLA8Nl+NtUVF0sA7MsXsP1UyJoMp4YLEuNSfAP+JcXn/tWtIaxVXM"
      crossorigin="anonymous"></script>
  </body>
</html>

```

# 5.Write a JavaScript program that displays an alert message to the user when they resize the browser window.

```javascript
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />

    <link
      href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css"
      rel="stylesheet"
      integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC"
      crossorigin="anonymous" />

    <title>Hello, world!</title>
  </head>
  <body>
    <h1>resize the page to check the alert</h1>
    <script>

      window.addEventListener("resize",()=>{alert("resize alert")})

    </script>
    <script
      src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/js/bootstrap.bundle.min.js"
      integrity="sha384-MrcW6ZMFYlzcLA8Nl+NtUVF0sA7MsXsP1UyJoMp4YLEuNSfAP+JcXn/tWtIaxVXM"
      crossorigin="anonymous"></script>
  </body>
</html>
```

# 6.Write a JavaScript program that uses AJAX to fetch and display data from a text file when the user clicks on a button.

```javascript
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <style>
      span {
        color: brown;
      }
    </style>
  </head>
  <body>
    <h2 id="text">
      If you click on this button text will be changed using
      <span>ajax</span>
    </h2>
    <button onclick="loadData()">Click Me</button>

    <script>
      function loadData() {
        xhttp = new XMLHttpRequest();

        xhttp.onreadystatechange = function() {
          if (this.readyState == 4 && this.status == 200) {
            document.getElementById("text").innerHTML = this.responseText;
          }
        };

        xhttp.open("GET","demo.txt",true);
        xhttp.send();
      }
    </script>
  </body>
</html>
```

# 7.Write a JavaScript program that uses AJAX to fetch and display an image from an API when the user clicks on a button.

```javascript
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <style>
      span {
        color: brown;
      }
      #btn {
      background-color: #4CAF50;
      border: none;
      color: white;
      padding: 15px 32px;
      text-align: center;
      text-decoration: none;
      display: inline-block;
      font-size: 16px;
      }
    </style>
  </head>
  <body>
    <h2 >
      If you click on 'click me' </click> button image will be shown using
      <span>ajax</span>
    </h2>
    <img id="text" src="" alt="">
    <br>
    <button onclick="loadData()" id="btn">Click Me</button>

    <script>
      function loadData() {
        xhttp = new XMLHttpRequest();

        xhttp.onreadystatechange = function() {
          if (this.readyState == 4 && this.status == 200) {
            document.getElementById("text").src = this.responseURL;
          }
        };

        xhttp.open("GET","https://source.unsplash.com/random/400x400/?code,laptop,phone,technology",true);
        xhttp.send();
      }
    </script>
  </body>
</html>
```
