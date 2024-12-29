# JavaScript Projects

## 07-projects/

### Project: To-Do List App (Beginner Level)\*\*

In this project, you will create a simple To-Do List app that allows users to add, remove, and mark tasks as complete. This project will help you practice basic JavaScript concepts, DOM manipulation, and event handling.

#### Features

- Add new tasks
- Remove tasks
- Mark tasks as complete/incomplete

#### Getting Started

1. **HTML Structure:**
   Create an `index.html` file with the following structure:

   ```html
   <!DOCTYPE html>
   <html lang="en">
     <head>
       <meta charset="UTF-8" />
       <meta name="viewport" content="width=device-width, initial-scale=1.0" />
       <title>To-Do List App</title>
       <link rel="stylesheet" href="styles.css" />
     </head>
     <body>
       <h1>To-Do List</h1>
       <input type="" id="taskInput" placeholder="Add a new task..." />
       <button id="addTaskButton">Add Task</button>
       <ul id="taskList"></ul>
       <script src="script.js"></script>
     </body>
   </html>
   ```

   JavaScript Logic: Create a script.js file to handle task management:

   ```js
   const taskInput = document.getElementById("taskInput");
   const addTaskButton = document.getElementById("addTaskButton");
   const taskList = document.getElementById("taskList");
   addTaskButton.addEventListener("click", () => {
     const task = taskInput.value;
     if (task) {
       const li = document.createElement("li");
       li.Content = task;
       li.addEventListener("click", () => {
         li.classList.toggle("completed");
       });
       taskList.appendChild(li);
       taskInput.value = "";
     }
   });
   ```

Create a styles.css file for basic styling:

```css
body {
  font-family: Arial, sans-serif;
  margin: 20px;
}

#taskList {
  list-style-type: none;
  padding: 0;
}

li {
  cursor: pointer;
  padding: 10px;
  border: 1px solid #ccc;
  margin-top: 5px;
}

.completed {
  -decoration: line-through;
  color: gray;
}
```

Project: Weather App (Intermediate Level)
In this project, you will build a weather application that fetches weather data from an API and displays it to the user. This project will help you learn about asynchronous programming, API calls, and working with JSON data.
Features:
Fetch weather data based on user input (city name)
Display current temperature and weather conditions
Handle errors (e.g., city not found)
Getting Started:
HTML Structure:
Create an index.html file:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Weather App</title>
    <link rel="stylesheet" href="styles.css" />
  </head>
  <body>
    <h1>Weather App</h1>
    <input type="" id="cityInput" placeholder="Enter city name..." />
    <button id="getWeatherButton">Get Weather</button>
    <div id="weatherResult"></div>
    <script src="script.js"></script>
  </body>
</html>
```

JavaScript Logic:
Create a script.js file to fetch weather data:

```js
const cityInput = document.getElementById("cityInput");
const getWeatherButton = document.getElementById("getWeatherButton");
const weatherResult = document.getElementById("weatherResult");

getWeatherButton.addEventListener("click", async () => {
  const cityName = cityInput.value;
  const apiKey = "YOUR_API_KEY"; // Replace with your OpenWeatherMap API key

  try {
    const response = await fetch(
      `https://api.openweathermap.org/data/2.5/weather?q=${cityName}&appid=${apiKey}&units=metric`
    );
    if (!response.ok) throw new Error("City not found");
    const data = await response.json();
    weatherResult.innerHTML = `
            <h2>${data.name}</h2>
            <p>Temperature: ${data.main.temp} °C</p>
            <p>Weather: ${data.weather.description}</p>
        `;
  } catch (error) {
    weatherResult.Content = error.message;
  }
});
```

Styling:
Create a styles.css file for basic styling:

```css
body {
  font-family: Arial, sans-serif;
  margin: 20px;
}

#weatherResult {
  margin-top: 20px;
  border: 1px solid #ccc;
  padding: 10px;
  display: inline-block;
}
```

Project: Single Page App with React (Advanced Level)
In this project, you will create a single-page application (SPA) using React. This project will help you understand component-based architecture, state management, and routing.
Features:
Create multiple components (e.g., Home, About, Contact)
Use React Router for navigation
Manage state using React hooks
Getting Started:
Set Up Your React Environment:
Use Create React App to set up your project:

```bash
npx create-react-app my-spa
cd my-spa
npm install react-router-dom
```

Create Components:
Inside the src folder, create three components (Home.js, About.js, Contact.js):

// Home.js

```js
import React from "react";

function Home() {
  return <h2>Home Page</h2>;
}

export default Home;
```

// About.js

```js
import React from "react";

function About() {
  return <h2>About Page</h2>;
}

export default About;
```

// Contact.js

```jsx
import React from "react";

function Contact() {
  return <h2>Contact Page</h2>;
}

export default Contact;
```

Set Up Routing in App.js:
Modify App.js to include routing:

```js
import React from "react";
import { BrowserRouter as Router, Route, Switch, Link } from "react-router-dom";
import Home from "./Home";
import About from "./About";
import Contact from "./Contact";

function App() {
  return (
    <Router>
      <nav>
        <Link to="/">Home</Link> |<Link to="/about">About</Link> |
        <Link to="/contact">Contact</Link>
      </nav>

      <Switch>
        <Route path="/" exact component={Home} />
        <Route path="/about" component={About} />
        <Route path="/contact" component={Contact} />
      </Switch>
    </Router>
  );
}

export default App;
```

Run Your Application:
Start your application using:

```bash
npm start
```

Conclusion
This section provides three hands-on projects that cater to different skill levels in JavaScript development. The To-Do List app is a great starting point for beginners to grasp fundamental concepts. The Weather app introduces intermediate developers to working with APIs and asynchronous programming. Finally, the Single Page App with React challenges advanced developers to utilize modern frameworks and routing techniques effectively.
