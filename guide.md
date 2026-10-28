# Web Application Development Lab: Codes, Procedure and Execution Guide

**Student:** Anushree Shinde | **PRN:** 25070122041 | **Sem:** III | **AY:** 2026-27

**Conventions used in this file**

- JavaScript (and all Node.js, MongoDB and HTML) code is copied **exactly** from your journal.
- CSS is **simplified slightly** (same look, fewer properties). The original CSS is not needed.
- Experiment 1 (handwritten) and Experiments 3, 4, 5 (Figma) contain no code, so they are not included.
- Commands are for **Windows 10/11** (the same as your journal).

## Contents

0. [Common Setup: VS Code, Node.js, Live Server](#0-common-setup)
1. [Experiment 2: Portfolio Web Page (HTML + CSS)](#experiment-2-portfolio-web-page-html--css)
2. [Experiment 6: JavaScript Programming](#experiment-6-javascript-programming)
3. [Experiment 7: Node.js HTTP Module, Routing, Form Validation](#experiment-7-nodejs-http-module-routing-and-form-validation)
4. [Experiment 8: Email Sending with Nodemailer](#experiment-8-automated-email-sending-using-nodejs-and-nodemailer)
5. [Experiment 9: MongoDB Installation and Basic Operations](#experiment-9-mongodb-installation-and-basic-operations-on-windows)
6. [Experiment 10: MongoDB CRUD Operations](#experiment-10-crud-operations-using-mongodb)
7. [Experiment 11: MongoDB Atlas + Node/Express Web App](#experiment-11-mongodb-atlas--nodejs--express-web-app)
8. [Experiment 12: Git, GitHub, Jenkins and Apache Tomcat](#experiment-12-git-github-jenkins-and-apache-tomcat)

---

## 0. Common Setup

### 0.1 Visual Studio Code

1. Download: <https://code.visualstudio.com/download> → **Windows → User Installer (x64)**.
2. Run the installer. On the *Select Additional Tasks* page, tick **Add to PATH** and **Add "Open with Code" action**.
3. Click **Install**, then **Finish**.

### 0.2 Node.js (needed for Exp 7, 8, 11)

1. Download: <https://nodejs.org/en/download> → choose **LTS** → **Windows Installer (.msi)**, 64-bit.
   (The exact file name changes with every version, so the download page is the stable link.)
2. Run the `.msi`, keep clicking **Next**, and keep **Add to PATH** ticked.
3. **Close every terminal and VS Code**, then open a new terminal and verify:

```bash
node -v
npm -v
```

Both should print version numbers.

| Error | Cause | Fix |
|---|---|---|
| `'node' is not recognized as an internal or external command` | Terminal was opened before install, or PATH was not added | Close and reopen the terminal and VS Code. If it still fails, re-run the installer and tick *Add to PATH*, or restart the PC. |
| `npm : File ...npm.ps1 cannot be loaded because running scripts is disabled` (PowerShell) | PowerShell execution policy | Run `Set-ExecutionPolicy -Scope CurrentUser RemoteSigned` in PowerShell and press `Y`. Or switch the VS Code terminal to **Command Prompt**. |
| `EADDRINUSE: address already in use :::3000` | An older server is still running on port 3000 | Press `Ctrl + C` in the old terminal, or run `taskkill /F /IM node.exe`, then start again. |

### 0.3 Live Server (optional, for HTML experiments)

1. In VS Code press `Ctrl + Shift + X`, search **Live Server** (by Ritwick Dey) and click **Install**.
   Marketplace page: <https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer>
2. Right-click the HTML file → **Open with Live Server**.

---

Experiment 1: HTML Page with Headings, Lists,Images,Tables,
Links, iFrame, Audio
Goal: one static page that uses every basic HTML element.
Steps
1. Create a folder lab1_html and open it in VS Code (File, then Open Folder).
2. Put an image named college.jpg and an audio file named sample.mp3 in the same
folder (any image and mp3 will do).
3. Create index.html and paste the code below.
4. Right-click the file, choose Open with Live Server (or just double-click the file).
5. Validate at validator.w3.org (use the "Validate by File Upload" tab) and fix any errors.

<!DOCTYPE html>
<html>
<head>
<title>Welcome to HTML</title>
</head>

<body>

<center>
<h1 style="color:rgb(90, 6, 90);">WELCOME TO HTML</h1>
</center>
<hr>

<h2 style="color:purple;">Content Heading 2</h2>

<h3 style="color:rgb(147, 2, 147);">Content Heading 3</h3>

<p style="color:violet;">
HTML means hypertext markup language. </p>

<h2>ORDERED LIST</h2>
<ol>
<li>HI</li>
<li>BYE</li>
</ol>

<h2>UNORDERED LIST</h2>
<ul>
<li>HI</li>
<li>BYE</li>
</ul>

<hr>

<h2>IMAGE</h2>
<img src="image.jpg" alt="Image Example" width="120">
<hr>

<h2>STUDENT TABLE</h2>
<table border="1" cellspacing="0" cellpadding="5">

<tr>
<th>PRN</th>
<th>Name</th>
<th>Age</th>
</tr>

<tr>
<td>067</td>
<td>Student</td>
<td>18</td>
</tr>
</table>

<hr>
<h2>AUDIO</h2>
<audio controls>
<source src="song.mp3" type="audio/mpeg">
Your browser does not support audio.
</audio>
<hr>

<h2>EMBEDDED WEBPAGE</h2>
<iframe src="name.html"
width="500"
height="300">

</iframe>

</body>
</html>

Assignment tips
Nested list: put a <ul> inside an <li> .
Caption: <figure><img src="college.jpg" alt="Campus"><figcaption>Our
campus</figcaption></figure>
Email link: <a href="mailto:you@example.com">Email me</a>
Google Map iframe: on Google Maps click Share, then Embed a map, copy the
<iframe> code.
Audio without autoplay: simply do not add the autoplay attribute.
Take a screenshot of the validator showing zero errors.
Note: some sites (for example Google and many banks) block iframes. Wikipedia and
Google Maps embeds work.

Experiment 3:Exploring the Figma Interface
Goal: learn the toolbar, panels, frames and layers. No commands needed; shortcuts are
listed.

Steps
1. Log in at figma.com, click New design file, and rename it Lab3_Exploration (click the
file name at the top).
2. Hover over each toolbar icon and note the tool name and shortcut.
3. Press F, and in the right panel pick a preset such as iPhone 14. A frame appears.
4. In the Layers panel (left), double-click the frame name and rename it Home Screen .
5. Inside the frame draw a rectangle (R) and an ellipse (O). In the right Design panel
change Fill, Corner radius, Stroke and Opacity.
6. Press T, click in the frame, and type a heading. Change font, size and colour in the Text
section.
7. Shift+click several layers, then press Ctrl/Cmd+G to group them. Notice the group in
Layers.
Tool Shortcut
Move V
Frame F
Rectangle R
Ellipse O
Pen P
Text T
Comment C
Group / Ungroup Ctrl/Cmd + G / Ctrl/Cmd + Shift + G
Frame selection Ctrl/Cmd + Alt + G
Section Shift + S
Pan Hold Space and drag
Zoom Ctrl/Cmd + scroll, or Ctrl/Cmd + plus/minus
8. Rename every layer meaningfully (for example Header Title , Hero Card ). Drag
layers up or down to change z-order (top of the list is the front). Select header
elements and press Ctrl/Cmd+Alt+G to make a sub-frame.
9. Practise zoom and pan.
10. Select 3 or 4 shapes and use the alignment buttons at the top of the Design panel
(align left, center, distribute vertical spacing).
11. Make a second frame, Login Screen , with a title text, two rectangles as input fields
and one rectangle with text as a button.
12. Select both frames, right-click, choose Section (or Shift+S), and name it Lab 3
Screens .
13. Figma auto-saves. Copy the file URL from the browser for submission.
Assignment: build three frames (Splash, Home, Profile) with at least 5 named layers each,
screenshot the Layers panel, and write one line per tool (Move, Frame, Rectangle, Ellipse,
Pen, Text, Comment, Layers).

Experiment 4:Wireframe, Mock-up and Reusable Components
Steps
1. In the Pages panel (top-left of Layers) click + and add a page named Wireframe .
2. Draw a grey-only wireframe of a Product Listing home screen: header box, search-bar
box, a 2-column grid of grey product-card rectangles with grey bars as text
placeholders, and a bottom navigation bar.
3. Add another page named Mockup . Recreate the screen in high fidelity with real
colours, a Google Font (Inter or Poppins), product images, and icons. For icons open
Plugins, then Browse plugins in Community, and install Iconify. Run it from Plugins,
then Iconify.
4. Button component: draw a rectangle, add the text Add to Cart , select both, and
press Ctrl/Cmd+Alt+K (Create component). Rename it Button/Primary .
5. Select the button and press Shift+A to applyAuto Layout. Set horizontal padding
about 24 and vertical padding about 12 so it grows with the text.
6. Open the Assets panel and drag two instances onto the canvas. Edit the text of one
and confirm the other and the main component stay unchanged.

7. Build a Product Card component: image placeholder, title text, price text, and a Button
instance inside. Select all and press Shift+A so the card auto-sizes, then
Ctrl/Cmd+Alt+K to make it a component.
8. Place multiple Product Card instances in the 2-column grid of the Mockup screen.
9. Keep all main components on a page or frame named Components and confirm they
show in the Assets panel.
Assignment: do three screens (Home, Details, Cart) in both wireframe and mock-up form,
and make at least three components (Button, Card, Navigation Bar), each used twice.
Screenshot before and after editing a main component to show all instances update.

Experiment 5:Interactive Prototype, Collaboration and Version
History
Steps
1. Open your Mockup page with the Home, Details and Cart screens.
2. In the right panel switch from Design to Prototype.
3. Select the Add to Cart button, then drag the small circle handle on its edge to the
Cart frame.
4. Set: Trigger On click, Action Navigate to, Destination Cart, Animation Smart animate,
Easing Ease in and out, Duration 300 ms.
5. Select a product card and connect it to Product Details with Slide in from the right.
6. On Product Details add a back icon and connect it to Home with Slide in from the left.
7. Interactive states: select the Button main component, click the + next to Variants (or
right-click, Add variant). Create variants named Default, Hover and Pressed with
different fills. In Prototype mode set the interaction While hovering, Change to, Hover.
8. Click the Present (play) icon top-right and click through Home, Details, Cart and back.
9. Click Share, add a classmate's email or copy the link, and set the permission to Can
edit. Both of you open the file and watch the live cursors as you move an object.
10. Press C to drop a comment on an element (for example "increase button size") and ask
your collaborator to reply.
11. Open File, then Show version history (or the clock icon) and click + to save a named
version such as Prototype v1 - navigation complete .
12. Change the background colour, save another named version, then open the earlier
version and click Restore this version to confirm rollback.

Assignment checklist: 4 or more connected screens, 6 or more interactions, 2 different
transition types, one component with 3 states, view-only versus edit-only sharing
compared, 2 named checkpoints visible in a Version History screenshot, plus the
prototype link.

## Experiment 2: Portfolio Web Page (HTML + CSS)

**Aim:** To design a personal portfolio web page using HTML5 and CSS3 (colours, borders, padding, gradients, box model, external CSS).

### Procedure

1. Create a folder `Portfolio_Website`.
2. Inside it create `portfolio.html` and `web.css` (the file names used in your screenshots).
3. Put your photo in the same folder and name it `profile.jpeg`.
4. Paste the HTML below into `portfolio.html` and the CSS into `web.css`.
5. The `<link rel="stylesheet" href="web.css">` tag connects the CSS file to the page.

### How to execute

- Double-click `portfolio.html`, **or** right-click it in VS Code → **Open with Live Server**.
- No terminal commands are needed.

### portfolio.html

```html
<!doctype html>
<html lang="en">

<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <link rel="stylesheet" href="web.css">
  <title>Portfolio</title>
</head>

<body>
  <center>
    <h2><span style="color: #7f3675">Anushree Shinde | Developer</span></h2>
    <img src="profile.jpeg" width="170" height="170" alt="Profile Picture">
  </center>
  <hr>

  <p><b>
      This is my portfolio. I am a student of Computer Science and Engineering.
      I currently study in second year at Symbiosis College. I have a keen interest in web
      development and programming. I am always eager to learn new
      technologies and enhancing my skills in the field of computer science. I am also interested in participating in
      coding competitions and hackathons to improve my problem solving abilities.
    </b></p>
  <hr>
  <h2>Personal Information</h2>

  <ul>
    <li><b>Name:</b> Anushree Shinde</li>
    <li><b>Date of Birth:</b> 09/10/2007</li>
    <li><b>Gender:</b> Female</li>
    <li><b>Address:</b> Pune, Maharashtra</li>
    <li><b>Mobile:</b> +91 7507507500</li>
    <li><b>Email:</b> anushree@gmail.com</li>
  </ul>
  <hr>
  <h2>Educational Qualification</h2>

  <table border="1" cellpadding="10" cellspacing="0">
    <tr>
      <th>Qualification</th>
      <th>Institute</th>
      <th>Board / University</th>
      <th>Year</th>
      <th>Percentage / CGPA</th>
    </tr>

    <tr>
      <td>BTECH Computer Engineering</td>
      <td>SIT College</td>
      <td>SIU</td>
      <td>Pursuing (2025-29)</td>
      <td>8.3</td>
    </tr>

    <tr>
      <td>12th</td>
      <td>SNBP School</td>
      <td>CBSE</td>
      <td>2025</td>
      <td>87%</td>
    </tr>

    <tr>
      <td>10th</td>
      <td>Euro School</td>
      <td>ICSE</td>
      <td>2023</td>
      <td>96.7%</td>
    </tr>
  </table>
  <hr>
  <h2>Skills</h2>
  <ul>
    <li>Programming Languages: C, C++, Java, Python</li>
    <li>Web Development: HTML, CSS, JavaScript</li>
    <li>Database Management: MySQL</li>
  </ul>
  <hr>
  <h2>Achievements</h2>

  <ul>
    <li>Received the Academic Excellence Award for outstanding performance.</li>
    <li>Secured First Place in a State-Level Coding Competition.</li>
    <li>Finalist in the National Hackathon Challenge.</li>
    <li>Certified in Python Programming by an online learning platform.</li>
    <li>Completed 100+ coding challenges on competitive programming platforms.</li>
    <li>Represented the college at a National Technical Symposium.</li>
    <li>Awarded Best Student Volunteer for organizing technical events.</li>
  </ul>
  <hr>

  <h2>Projects</h2>

  <table border="1" cellpadding="10" cellspacing="0">
    <tr>
      <th>Project Name</th>
      <th>Description</th>
    </tr>

    <tr>
      <td>Portfolio Website</td>
      <td>Responsive personal portfolio using HTML and CSS.</td>
    </tr>

    <tr>
      <td>Student Management System</td>
      <td>Application to manage student records.</td>
    </tr>

    <tr>
      <td>Weather App</td>
      <td>Displays weather information using APIs.</td>
    </tr>
  </table>
  <hr>
  <h2>Certifications</h2>

  <ol>
    <li>Oracle Certified Java Programmer</li>
    <li>Google Data Analytics Professional Certificate</li>
    <li>AWS Cloud Practitioner Essentials</li>
    <li>Python for Everybody Certification</li>
    <li>Full Stack Web Development Certification</li>
  </ol>

  <hr>
  <center>
    Connect with me on :
    <a href="https://github.com/anushree0910">GitHub</a>
    /
    <a href="https://www.linkedin.com/in/anushree-shinde-362bba368">LinkedIn</a>
  </center>
  <hr>

</body>
</html>
```

### web.css (simplified)

```css
body {
    font-family: Arial, sans-serif;
    margin: 20px;
    background-color: #ece0eb;
}

img {
    border-radius: 50%;
    border: 5px solid #c89bdc;
    margin: 10px 0;
}

ul, ol {
    background-color: #fff8fe;
    padding: 20px 40px;
    border: 2px solid #d8b4e2;
    border-radius: 8px;
}

p {
    line-height: 1.7;
}

th {
    background: #9b59b6;
    color: white;
}

td {
    background: #f8f0ff;
}
```

**What was simplified:** removed the unused `header` rule (the HTML has no `<header>` tag), the `box-shadow`, the `li` padding, and the invalid `text-align: 1;` line.

### Common errors

| Problem | Fix |
|---|---|
| Profile picture shows a broken icon | The file must be named exactly `profile.jpeg` (not `.jpg` or `.png`) and sit in the same folder as `portfolio.html`. |
| Page has no colours | `web.css` must be in the same folder, and the link must say `href="web.css"`. |

---

## Experiment 6: JavaScript Programming

**Aim:** To develop JavaScript programs using variables, arrays, loops, functions, events, DOM manipulation and form validation.

There are **three programs**: (1) Login page, (2) JavaScript function example, (3) `document.write()` example.

### Procedure

**Program 1: Login page**

1. Create a folder (for example `Exp6_Login`) and open it in VS Code.
2. Create three files: `index.html`, `style.css`, `script.js`.
3. Paste the code of each file from below.
4. `index.html` links the CSS with `<link>` and the JavaScript with `<script src="script.js">`.
5. The form's `onsubmit="return validateLogin()"` calls the function. The function returns `false` so the page does not reload.

**Program 2 and 3**

1. Create two new HTML files, `function.html` and `write.html`.
2. Paste the code below. Each file is self-contained (no CSS or JS file needed).

### How to execute

- Open `index.html` (or `function.html`, `write.html`) with **Live Server**, or double-click the file.
- **Test cases for the login page**
  - `Anushree` / `1234` → "Login Successful"
  - `Student` / `5678` → "Login Successful"
  - Wrong username or password → "ERROR / User is invalid"
  - Empty fields → "Please enter username and password."

### 1. Login page

**index.html**

```html
<!DOCTYPE html>
<html>

<head>
    <title>Login Page</title>
    <link rel="stylesheet" href="style.css">
</head>

<body>

    <div class="login-box">

        <h1>Welcome Back</h1>

        <p>Sign in to continue</p>

        <form onsubmit="return validateLogin()">

            <label>Username</label>

            <input type="text"
                   id="username"
                   placeholder="Enter username">

            <label>Password</label>

            <input type="password"
                   id="password"
                   placeholder="Enter password">

            <button type="submit">
                LOGIN
            </button>

        </form>

    </div>

    <script src="script.js"></script>

</body>

</html>
```

**style.css (simplified)**

```css
* {
    box-sizing: border-box;
}

body {
    margin: 0;
    min-height: 100vh;
    background: #eee9ff;
    display: flex;
    justify-content: center;
    align-items: center;
    font-family: Arial, sans-serif;
}

.login-box {
    width: 380px;
    padding: 40px;
    background: white;
    border-radius: 20px;
    text-align: center;
}

h1 {
    color: #302b4a;
}

p {
    color: #858092;
}

label {
    display: block;
    text-align: left;
    margin-top: 18px;
    margin-bottom: 6px;
}

input {
    width: 100%;
    padding: 12px;
    border: 1px solid #ccc;
    border-radius: 10px;
}

button {
    width: 100%;
    padding: 12px;
    margin-top: 25px;
    border: none;
    border-radius: 10px;
    background: #6554b8;
    color: white;
    cursor: pointer;
}
```

**script.js**

```javascript
let users = [
    {
        username: "Anushree",
        password: "1234"
    },

    {
        username: "Student",
        password: "5678"
    }
];


function validateLogin()
{
    let username =
        document.getElementById("username").value;

    let password =
        document.getElementById("password").value;

    let found = false;

    for(let i = 0; i < users.length; i++)
    {
        if(users[i].username == username &&
           users[i].password == password)
        {
            found = true;
            break;
        }
    }

    if(username == "" || password == "")
    {
        window.alert("Please enter username and password.");
    }
    else if(found == true)
    {
        window.alert("Login Successful");
    }
    else
    {
        window.alert("ERROR\nUser is invalid");
    }

    return false;
}
```

### 2. JavaScript function example (`function.html`)

```html
<!DOCTYPE html>
<html>
<head>
    <title>JavaScript Function</title>

    <script>
        function myFunction()
        {
            document.getElementById("demo").innerHTML =
                "Text Changed Successfully!";
        }
    </script>
</head>

<body style="text-align:center; background-color:#f3e8ff;">

    <h2 style="color:#6a1b9a;">
        JavaScript Function in the Head
    </h2>

    <h1 id="demo">
        Original Text
    </h1>

    <button onclick="myFunction()" style="
        background-color:#8e44ad;
        color:white;
        border:none;
        padding:10px 20px;
        border-radius:5px;
    ">
        Click Me
    </button>

</body>
</html>
```

### 3. `document.write()` example (`write.html`)

```html
<!DOCTYPE html>
<html>

<head>
    <title>JavaScript Calculation</title>
</head>

<body style="
    text-align: center;
    background-color: #e8f4ff;
">

    <h2 style="color: #063e7e;">
        JavaScript Calculation
    </h2>

    <h1>
        Addition of Two Numbers
    </h1>

    <p style="color: #063e7e;">
        First Number: 15 ,
        Second Number: 10
    </p>

    <script>

        let num1 = 15;
        let num2 = 10;

        let sum = num1 + num2;

        document.write("Sum = ",sum);

    </script>

</body>
</html>
```
1. JavaScript function and onclick event
File name: JS_function.html

<!DOCTYPE html>
<html>
<head>
    <title>JavaScript Function</title>

    <script>
        function myFunction() {
            document.getElementById("demo").innerHTML =
                "Paragraph changed.";
        }
    </script>
</head>

<body>
    <h2>Demo JavaScript in Head</h2>

    <p id="demo">A Paragraph</p>

    <button onclick="myFunction()">Try it</button>
</body>
</html>

2. JavaScript window.alert()
File name: alert_example.html
<!DOCTYPE html>
<html>
<head>
    <title>JavaScript Alert</title>
</head>

<body>
    <h2>JavaScript Alert</h2>

    <button onclick="window.alert('I am an alert box!')">
        Try it
    </button>
</body>
</html>

3. JavaScript innerHTML
File name: innerHTML_example.html
<!DOCTYPE html>
<html>
<head>
    <title>JavaScript innerHTML</title>
</head>

<body>
    <h2>JavaScript innerHTML</h2>

    <p id="demo">Original Text</p>

    <button onclick="changeText()">Change Text</button>

    <script>
        function changeText() {
            document.getElementById("demo").innerHTML =
                "<b>Hello World!</b>";
        }
    </script>
</body>
</html>

4. JavaScript innerText
File name: innerText_example.html

<!DOCTYPE html>
<html>
<head>
    <title>JavaScript innerText</title>
</head>

<body>
    <h2>JavaScript innerText</h2>

    <p id="demo">Original Text</p>

    <button onclick="changeText()">Change Text</button>

    <script>
        function changeText() {
            document.getElementById("demo").innerText =
                "Hello World!";
        }
    </script>
</body>
</html>

5. JavaScript document.write()
File name: document_write.html

<!DOCTYPE html>
<html>
<head>
    <title>JavaScript document.write()</title>
</head>

<body>
    <h2>JavaScript document.write()</h2>

    <script>
        document.write("Result: " + (5 + 6));
    </script>
</body>
</html>

6. JavaScript console.log()
File name: console_log.html

<!DOCTYPE html>
<html>
<head>
    <title>JavaScript console.log()</title>
</head>

<body>
    <h2>JavaScript console.log()</h2>

    <p>Open the browser console to see the output.</p>

    <script>
        console.log(5 + 6);
        console.log("Hello World!");
    </script>
</body>
</html>

### Common errors

| Problem | Fix |
|---|---|
| Button does nothing / no alert | Check the browser console (`F12` → Console). Usually `script.js` is not linked, or the file name does not match exactly. |
| `validateLogin is not defined` | `<script src="script.js">` must be present and `script.js` must be in the same folder as `index.html`. |
| Page reloads after clicking LOGIN | Make sure the form uses `onsubmit="return validateLogin()"` (with `return`) and the function ends with `return false;`. |

---

## Experiment 7: Node.js HTTP Module, Routing and Form Validation

**Aim:** To implement a server-side web application using the native Node.js `http` module, demonstrating URL routing, form handling and server-side validation.

There are **three programs**. All three use **port 3000**, so run **one at a time** (stop one with `Ctrl + C` before starting the next).

### Procedure

1. Install Node.js first (see [0.2](#02-nodejs-needed-for-exp-7-8-11)).
2. Create a folder `Exp7_NodeJS` and open it in VS Code.
3. Create these files in it:
   - `basic.js` (Program 1)
   - `routing.js` (Program 2)
   - `form.js` (Program 3)
   - `style.css` (used by Program 2 and 3)
4. Paste the code below into each file.
5. Open the terminal in VS Code (`Ctrl + ~`). Make sure it is inside `Exp7_NodeJS`.

### How to execute

```bash
# Program 1: basic server
node basic.js
# open http://localhost:3000

# Program 2: URL routing (press Ctrl+C to stop the previous one first)
node routing.js
# open http://localhost:3000/  /about  /contact  and any wrong URL like /xyz

# Program 3: form handling and validation
node form.js
# open http://localhost:3000, fill the form, and also try leaving a field empty
```

Leave the terminal running while you test in the browser. Stop with `Ctrl + C`.

### Program 1: Basic web server (`basic.js`)

```javascript
const http = require('http');


const server = http.createServer((req, res) => {


    res.write(`
        <html>
        <head>
            <title>First Node.js Server</title>
        </head>
        <body>
            <h1>Welcome to Node.js</h1>
            <p>This is my first web server using the HTTP module.</p>
            <p>Server is running successfully!</p>
        </body>
        </html>
    `);


    res.end();
});


server.listen(3000, () => {
    console.log('Server running at http://localhost:3000');
});
```

### Program 2: URL routing (`routing.js`)

```javascript
const http = require('http');
const fs = require('fs');


const server = http.createServer((request, response) => {


    // Serve CSS file
    if (request.url === '/style.css') {


        response.writeHead(200, { 'Content-Type': 'text/css' });


        const css = fs.readFileSync('style.css');


        response.write(css);


        response.end();


    }


    else {


        response.writeHead(200, { 'Content-Type': 'text/html' });


        if (request.url === '/') {


            response.write(`
                <html>
                <head>
                    <title>Home Page</title>
                    <link rel="stylesheet" href="/style.css">
                </head>


                <body>


                    <div class="container">


                        <h1>Home Page</h1>
                        <hr>
                        <p>Welcome to my Node.js application.</p>


                    </div>


                </body>
                </html>
            `);


        }


        else if (request.url === '/about') {


            response.write(`
                <html>
                <head>
                    <title>About Page</title>
                    <link rel="stylesheet" href="/style.css">
                </head>


                <body>


                    <div class="container">


                        <h1>About Page</h1>
                        <hr>
                        <p>
                        This application is created using Node.js.
                        Node.js is a free, open-source, and cross-platform JavaScript runtime environment that executes JavaScript code outside of a web browser.
                        It allows developers to use JavaScript for server-side scripting and backend development, enabling the creation of dynamic web page content before the page is sent to the user's web browser.
                        </p>


                        <a href="/"><u>Home</u></a>


                    </div>


                </body>
                </html>
            `);


        }


        else if (request.url === '/contact') {


            response.write(`
                <html>
                <head>
                    <title>Contact Page</title>
                    <link rel="stylesheet" href="/style.css">
                </head>


                <body>


                    <div class="container">


                        <h1>Contact Page</h1>
                        <hr>
                        <p>
                        Email: anushree.shinde.btech2025@sitpune.edu.in <br><br>
                        Phone: 829111****
                        </p>


                        <a href="/"><u>Home</u></a>


                    </div>


                </body>
                </html>
            `);


        }


        else {


            response.write(`
                <html>
                <head>
                    <title>404</title>
                    <link rel="stylesheet" href="/style.css">
                </head>


                <body>


                    <div class="container">


                        <h1 class="error">404 - Page Not Found</h1>


                        <p>The requested page does not exist.</p>


                        <a href="/"><u>Go To Home</u></a>


                    </div>


                </body>
                </html>
            `);


        }
        response.end();
    }
});


server.listen(3000, () => {
    console.log('Server is running at http://localhost:3000');
});
```

### Program 3: Form handling and validation (`form.js`)

```javascript
const http = require('http');
const querystring = require('querystring');
const fs = require('fs');


const server = http.createServer((request, response) => {


    // CSS file
    if (request.url === '/style.css') {


        response.writeHead(200, { 'Content-Type': 'text/css' });
        response.end(fs.readFileSync('style.css'));


    }


    // Registration Form
    else if (request.method === 'GET' && request.url === '/') {


        response.writeHead(200, { 'Content-Type': 'text/html' });


        response.end(`
            <html>
            <head>
                <title>Course Registration</title>
                <link rel="stylesheet" href="/style.css">
            </head>


            <body>


                <div class="container">


                    <h1>Course Registration</h1>


                    <form method="POST" action="/register">


                        <label>Student Name:</label>
                        <input type="text" name="name">


                        <label>Course:</label>
                        <input type="text" name="course">


                        <label>Phone Number:</label>
                        <input type="text" name="phone">


                        <input type="submit" value="Register">


                    </form>


                </div>


            </body>
            </html>
        `);
    }


    // Process Registration
    else if (request.method === 'POST' && request.url === '/register') {


        let body = '';


        request.on('data', (chunk) => {
            body += chunk.toString();
        });


        request.on('end', () => {


            const data = querystring.parse(body);


            const name = data.name;
            const course = data.course;
            const phone = data.phone;


            response.writeHead(200, { 'Content-Type': 'text/html' });


            if (!name || !course || !phone) {


                response.end(`
                    <html>
                    <head>
                        <link rel="stylesheet" href="/style.css">
                    </head>


                    <body>
                        <div class="container">
                            <h1 class="error">Registration Failed</h1>
                            <p>Please fill all the fields.</p>
                            <a href="/"><u>Go Back</u></a>
                        </div>
                    </body>
                    </html>
                `);
            } else {


                response.end(`
                    <html>
                    <head>
                        <link rel="stylesheet" href="/style.css">
                    </head>


                    <body>
                        <div class="container">
                            <h1 class="success">Registration Successful!</h1>


                            <p><b>Name:</b> ${name}</p>
                            <p><b>Course:</b> ${course}</p>
                            <p><b>Phone:</b> ${phone}</p>


                            <a href="/"><u>Register Another Student</u></a>
                        </div>
                    </body>
                    </html>
                `);
            }
        });
    }


    // 404 Page
    else {


        response.writeHead(404, { 'Content-Type': 'text/html' });


        response.end(`
            <html>
            <head>
                <link rel="stylesheet" href="/style.css">
            </head>


            <body>
                <div class="container">
                    <h1 class="error">404 - Page Not Found</h1>
                    <p>The requested page does not exist.</p>
                    <a href="/"><u>Go to Home</u></a>
                </div>
            </body>
            </html>
        `);
    }


});


server.listen(3000, () => {
    console.log('Server running at http://localhost:3000');
});
```

### style.css (simplified)

```css
body {
    font-family: Arial, sans-serif;
    background: #fce4ec;
    text-align: center;
    padding: 40px;
}

.container {
    width: 400px;
    margin: auto;
    background: white;
    padding: 30px;
    border-radius: 15px;
}

h1 {
    color: #7b1fa2;
}

a {
    display: inline-block;
    margin: 10px;
    color: #7b1fa2;
    text-decoration: none;
}

label {
    display: block;
    text-align: left;
    margin-top: 15px;
}

input[type="text"] {
    width: 100%;
    padding: 10px;
    margin-top: 5px;
    box-sizing: border-box;
    border: 1px solid #ccc;
    border-radius: 8px;
}

input[type="submit"] {
    width: 100%;
    padding: 10px;
    margin-top: 20px;
    border: none;
    border-radius: 20px;
    background: #7b1fa2;
    color: white;
}

.error {
    color: red;
}

.success {
    color: green;
}
```

### Common errors

| Error | Cause | Fix |
|---|---|---|
| Browser: `ERR_CONNECTION_REFUSED` | The server is not running (never started, crashed, or stopped) | Run `node routing.js` from inside the project folder and **leave the terminal open**. Check the terminal for a crash message. |
| Terminal: `Error: ENOENT: no such file or directory, open 'style.css'` (server crashes) | `style.css` is missing or in a different folder | Put `style.css` in the **same folder** as the `.js` file and run `node` from that folder. |
| `EADDRINUSE: address already in use :::3000` | Another program (or an earlier run) is using port 3000 | `Ctrl + C` in the old terminal, or `taskkill /F /IM node.exe`. |
| `Cannot find module 'C:\...\routing.js'` | Terminal is in the wrong folder, or file name is wrong | `cd` into the folder (`cd Exp7_NodeJS`) and check the file name with `dir`. |
| Page appears but has no colours | `/style.css` was not served | Check the CSS file name and location; hard-refresh with `Ctrl + F5`. |

> **Optional improvements (not in your journal):** in Program 2 the 404 page is sent with status `200` (change `response.writeHead(200, ...)` to `404` for the 404 branch), and in Program 3 you can use `.trim()` on the fields so space-only input is rejected.

---

## Experiment 8: Automated Email Sending using Node.js and Nodemailer

**Aim:** To send automated emails from a Node.js application using the Nodemailer module and the Gmail SMTP server.

### Part A: Generate a Google App Password

Gmail does not accept your normal password in code. You need an **App Password**.

1. Sign in to the Google account you will send from.
2. Turn on **2-Step Verification**: <https://myaccount.google.com/signinoptions/two-step-verification>
3. Open the App Passwords page: <https://myaccount.google.com/apppasswords>
4. Type an app name (for example `nodemailer`) and click **Create**.
5. Google shows a **16-character password** (written in groups of four). Copy it and **remove the spaces** when pasting into the code.
6. Treat it like a password. Do not share it, post it, or put it in screenshots.

> **Security warning:** the screenshot in your submitted PDF shows a real App Password. Anyone who sees it can send mail as you. Go to <https://myaccount.google.com/apppasswords>, **delete** that password, and create a new one. Use the placeholder version below in anything you share.

### Part B: Procedure

1. Create a folder `Exp8_Email` and open it in VS Code.
2. Open the terminal inside the folder and run:

```bash
npm init -y
npm install nodemailer
```

3. Create `sendEmail.js` and paste the code below.
4. Replace `YOUR_APP_PASSWORD` with your 16-character App Password (no spaces), and set `user`, `from` and `to` to your own addresses.

### How to execute

```bash
node sendEmail.js
```

Expected terminal output:

```
Email sent successfully!
250 2.0.0 OK  ...  gsmtp
```

Then check the receiver's **Inbox or Spam** folder and the sender's **Sent** folder.

### sendEmail.js

```javascript
const nodemailer = require('nodemailer');

const transporter = nodemailer.createTransport({
    service: 'gmail',
    auth: {
        user: 'anushree.shinde.btech2025@sitpune.edu.in',
        pass: 'YOUR_APP_PASSWORD'
    }
});

const mailOptions = {
    from: 'anushree.shinde.btech2025@sitpune.edu.in',
    to: 'shindeanushree04@gmail.com',
    subject: 'Automated Email using Node.js',
    text: 'Hello! This email was sent automatically using Node.js and Nodemailer.'
};

transporter.sendMail(mailOptions, (error, info) => {
    if (error) {
        console.log('Error:', error);
    } else {
        console.log('Email sent successfully!');
        console.log(info.response);
    }
});
```

### Common errors

| Error | Cause | Fix |
|---|---|---|
| `Cannot find module 'nodemailer'` | Package not installed in this folder | Run `npm install nodemailer` **inside the same folder** as `sendEmail.js`. |
| `Invalid login: 535-5.7.8 Username and Password not accepted` | Normal password used, spaces in the App Password, or wrong email | Use the **16-character App Password** with no spaces, and make sure `user` is the account that created it. |
| App Passwords page says the setting is "not available for your account" | 2-Step Verification is off, or a college/work (Google Workspace) admin has disabled App Passwords | Turn on 2-Step Verification. If it is a college account, ask the admin, or use a personal `@gmail.com` account as the sender. |
| `ETIMEDOUT` / `ECONNECTION` / `ENOTFOUND smtp.gmail.com` | No internet, or a firewall/college Wi-Fi blocks SMTP | Try a mobile hotspot or another network. Allow Node.js through the firewall. |
| Email "sent" but not in Inbox | Landed in Spam | Check the **Spam** folder and mark it "Not spam". |
| `npm : ...npm.ps1 cannot be loaded` | PowerShell script policy | See the fix in [0.2](#02-nodejs-needed-for-exp-7-8-11). |

---

## Experiment 9: MongoDB Installation and Basic Operations on Windows

**Aim:** To install MongoDB Community Server and MongoDB Shell (`mongosh`) on Windows, connect to the local server and perform basic database operations.

### Part A: Install MongoDB Community Server

1. Open the download page: <https://www.mongodb.com/try/download/community>
2. Select **Version:** (current, latest), **Platform:** *Windows x64*, **Package:** *msi*, then click **Download**.
3. Run the downloaded `.msi` and click **Next**. Accept the licence agreement.
4. Choose setup type **Complete**.
5. On *Service Configuration*:
   - Keep **Install MongoDB as a Service** ticked.
   - Select **Run service as Network Service user**.
   - Keep the service name as **MongoDB**.
6. On the last page you may **untick "Install MongoDB Compass"** (optional GUI; not needed for the lab).
7. Click **Install** (allow the admin prompt), then **Finish**.
8. Verify the service is running:
   - Press `Win + R`, type `services.msc`, press Enter.
   - Find **MongoDB Server (MongoDB)** and check that the status is **Running**.
9. Verify the installation folder exists: `C:\Program Files\MongoDB\Server\<version>\bin`.

### Part B: Install MongoDB Shell (mongosh)

1. Open: <https://www.mongodb.com/try/download/shell>
2. Select **Platform:** *Windows 64-bit (10+)*, **Package:** *MSI*, then click **Download**.
3. Run the installer. When asked, keep the option to **add mongosh to the PATH** enabled.
4. Open a **new** Command Prompt and verify:

```bash
mongosh --version
```

Reference for the shell: <https://www.mongodb.com/docs/mongodb-shell/>

### Part C: Commands (as in your journal)

Run `mongosh` in Command Prompt. The lines below it are typed **inside** the `mongosh` prompt.

```bash
mongosh
```

```javascript
use college
db.students.insertOne({name: "Anushree", age: 19, department: "CSE"})
show dbs
show collections
db.students.find()
db
db.stats()
db.dropDatabase()
show dbs
```

| Command | What it does |
|---|---|
| `mongosh` | Connects to the local server at `127.0.0.1:27017` |
| `use college` | Switches to the `college` database (it is only saved once data is inserted) |
| `db.students.insertOne({...})` | Inserts one student document and creates the collection |
| `show dbs` | Lists databases (`college` appears after the insert) |
| `show collections` | Lists collections in the current database |
| `db.students.find()` | Shows all student documents |
| `db` | Shows the current database name |
| `db.stats()` | Shows statistics of the current database |
| `db.dropDatabase()` | Deletes the current database (check `db` first) |

### Common errors

| Error | Cause | Fix |
|---|---|---|
| `'mongosh' is not recognized...` | mongosh not on PATH, or terminal opened before install | Close and open a **new** Command Prompt. If it still fails, add `C:\Program Files\mongosh\` to PATH (Start → "Edit the system environment variables" → Environment Variables → Path → New). |
| `MongoNetworkError: connect ECONNREFUSED 127.0.0.1:27017` | The MongoDB service is not running | Open `services.msc` → right-click **MongoDB Server** → **Start**. Or in an **Administrator** Command Prompt run `net start MongoDB`. |
| Installer rolls back or stops with an error | Not run as admin, or antivirus interfering | Right-click the MSI → **Run as administrator**. Temporarily pause antivirus. Untick Compass and retry. |
| Service will not start | Port 27017 busy, or a broken data folder | Check `netstat -ano \| findstr 27017`. Restart the PC, then start the service again. |
| `show dbs` does not list `college` | No data inserted yet (databases are created lazily) | Run the `insertOne` command first, then `show dbs`. |
| Startup warning "Access control is not enabled for the database" | Normal for a local lab setup | It is only a warning. Safe to ignore for this experiment. |

---

## Experiment 10: CRUD Operations using MongoDB

**Aim:** To perform Create, Read, Update and Delete (CRUD) operations on documents in MongoDB using the MongoDB Shell.

**Requires:** MongoDB Server and `mongosh` from Experiment 9. Database: `collegeDB`. Collections: `students` and `teachers`.

### Procedure

1. Open Command Prompt and run `mongosh`.
2. Select the database with `use collegeDB` and run `show dbs`.
3. Create the `students` and `teachers` collections, then verify with `show collections`.
4. Insert multiple students and multiple teachers with `insertMany()`.
5. Read all documents with `find()`.
6. Update one teacher and one student with `updateOne()`, and verify with `findOne()`.
7. Search students by department with `find()`.
8. Insert one student with `insertOne()`, delete it with `deleteOne()`, and count with `countDocuments()`.
9. Drop the `teachers` collection with `drop()` and verify.
10. Show selected fields sorted by age using projection and `sort()`.
11. Update many with `updateMany()`, then delete many with `deleteMany()`, and verify.
12. Drop the database with `dropDatabase()` and verify with `show dbs`.
db.collection.find(query).pretty()

### How to execute

Run `mongosh` once. Then paste each block below, **one at a time**, at the `mongosh` prompt (multi-line commands can be pasted directly).

```bash
mongosh
```

### Commands (in order, as in your screenshots)

```javascript
// 1. Select database and list databases
use collegeDB
show dbs
```

> `collegeDB` appears in `show dbs` only after the first collection/data is created (next step).

```javascript
// 2. Create collections and verify
db.createCollection("students")
db.createCollection("teachers")
show collections
```

```javascript
// 3. Insert multiple students
db.students.insertMany([
    {name: "Anushree", age: 19, dept: "CSE", year: 3},
    {name: "Natasha", age: 21, dept: "IT", year: 2},
    {name: "Anish", age: 18, dept: "CSE", year: 2}
])
```

```javascript
// 4. Insert multiple teachers
db.teachers.insertMany([
    {name: "Ankur Goyal", subject: "Web Application Development", dept: "CSE"},
    {name: "Arijit Dutta", subject: "Java", dept: "IT"}
])
```

```javascript
// 5. Read all documents
db.students.find()
db.teachers.find()
```

```javascript
// 6. Update one teacher and verify
db.teachers.updateOne(
    {name: "Ankur Goyal"},
    {$set: {subject: "Full Stack"}}
)
db.teachers.findOne ({name: "Ankur Goyal"})
```

```javascript
// 7. Update one student and verify
db.students.updateOne(
    {name: "Anushree"},
    {$set: {year: 4}}
)
db.students.findOne ({name: "Anushree"})
```

```javascript
// 8. Search students by department
db.students.find ({dept: "CSE"})
```

```javascript
// 9. Insert one student
db.students.insertOne ({
    name: "Anwesha",
    age: 18,
    dept: "IT",
    year: 3
})
```

```javascript
// 10. Delete that student
db.students.deleteOne({name: "Anwesha"})
```

```javascript
// 11. Count students
db.students.countDocuments({})
```

```javascript
// 12. Drop the teachers collection and verify
db.teachers.drop()
show collections
```

```javascript
// 13. Projection and sorting (selected fields, sorted by age)
db.students.find(
    {},
    {name: 1, dept: 1, age: 1, _id: 0}
).sort({age: 1})
```

```javascript
// 14. Update many students and verify
db.students.updateMany(
    {dept: "CSE"},
    {$set: {dept: "CSE & AI"}}
)
db.students.find ({dept: "CSE & AI"})
```

```javascript
// 15. Delete many students and verify the remaining ones
db.students.deleteMany({dept: "CSE & AI"})
db.students.find ()
```

```javascript
// 16. Drop the database and verify
db.dropDatabase()
show dbs
```

**Expected results (from your screenshots)**

- Step 3 → `acknowledged: true` with 3 inserted ids; Step 4 → 2 inserted ids.
- Step 11 → `3`.
- Step 13 → Anish (18), Anushree (19), Natasha (21).
- Step 14 → `matchedCount: 2, modifiedCount: 2`; Step 15 → `deletedCount: 2`, only Natasha remains.
- Step 16 → `{ ok: 1, dropped: 'collegeDB' }`.

> The `_id` values (ObjectId) will be different on your machine; that is normal.

### Common errors

| Error | Cause | Fix |
|---|---|---|
| `MongoNetworkError ... ECONNREFUSED 127.0.0.1:27017` | MongoDB service not running | `net start MongoDB` in an admin Command Prompt (see Experiment 9). |
| `MongoServerError: Collection already exists` | `createCollection` run twice | Not a problem. Use `show collections` to confirm and continue. |
| `show dbs` does not list `collegeDB` | No data/collection yet | Create the collections or insert data first. |
| `find()` returns nothing after `deleteMany` | All matching documents were removed | Re-run the `insertMany` step to restore data. |
| `SyntaxError: Unexpected token` when pasting | Commands pasted with a stray `// comment` line breaking a block, or half a block pasted | Paste **one block at a time** and copy the full block including the closing `)`. |
| Wrong database is being modified | You are not in `collegeDB` | Type `db` to check the current database; use `use collegeDB` to switch. |

---

## Experiment 11: MongoDB Atlas + Node.js + Express Web App

**Aim:** To create a MongoDB Atlas cluster, connect it to a Node.js/Express web application and insert, retrieve and delete student records.

**Database:** `collegeDB` | **Collection:** `students` | **Project folder:** `Wad_ass11`

### Part A: Set up MongoDB Atlas (cloud database)

1. Create a free account: <https://www.mongodb.com/cloud/atlas/register>
   (Direct login page afterwards: <https://cloud.mongodb.com>)
2. **Create the cluster**
   - Click **Create** (or **Build a Database**), choose the **M0 Free** tier.
   - Name the cluster **Cluster0**, choose a provider and a nearby region (for example AWS, Mumbai), then click **Create Deployment**.
   - Wait until the cluster status shows it is ready.
3. **Database user** (left menu → **Database Access** → **Add New Database User**)
   - Authentication method: **Password**.
   - Enter a username and a password. Prefer a password **without special characters** (such as `@ : / ?`) to avoid connection-string problems.
   - Role: **Read and write to any database**. Click **Add User**.
4. **Network access** (left menu → **Network Access** → **Add IP Address**)
   - Click **Add Current IP Address** → **Confirm**.
   - Wait until the status becomes **Active**.
   - Your IP changes when you switch Wi-Fi or hotspot. Add the new IP again if the connection suddenly fails. For lab practice you may also use `0.0.0.0/0` (allow from anywhere), but never keep that for real projects.
5. **Connection string**
   - Go to your cluster → click **Connect** → **Drivers** → select **Node.js**.
   - Copy the string. It looks like `mongodb+srv://<username>:<password>@cluster0.xxxxx.mongodb.net/?appName=Cluster0`.
   - Replace `<username>` and `<password>` with your database user's details (remove the `<` `>` signs).

> The Atlas screens are redesigned from time to time, so button names can differ slightly, but the flow is always: **cluster → database user → IP access → connection string**.

### Part B: Create the project

1. Create the folder `Wad_ass11` and open it in VS Code.
2. Create this structure:

```
Wad_ass11
├── .env
├── server.js
├── package.json        (created by npm init)
├── node_modules        (created by npm install)
└── public
    └── index.html
```

3. In the VS Code terminal (inside `Wad_ass11`):

```bash
npm init -y
npm install express mongodb dotenv
```

4. Create the file `.env` (exactly this name, no `.txt`) in the project root, next to `server.js`:

```
MONGODB_URI=mongodb+srv://<username>:<password>@cluster0.xxxxx.mongodb.net/?appName=Cluster0
```

   - No quotes, no spaces around `=`, and no `<` `>` signs. Never upload this file to GitHub.

5. Create `server.js` and `public/index.html` using the code below.

### How to execute

```bash
node server.js
```

Expected terminal output:

```
Connected to MongoDB Atlas
Server running at http://localhost:3000
```

1. Open <http://localhost:3000> in Chrome.
2. Enter name, roll number and course, then click **Add Student**.
3. Click **Refresh Students** to load the table; click **Delete** to remove a row.
4. Verify in Atlas: cluster → **Browse Collections** → `collegeDB` → `students`.

### Backend: server.js

```javascript
const express = require("express");
const { MongoClient, ObjectId } = require("mongodb");
require("dotenv").config();


const app = express();
const PORT = 3000;


// Middleware
app.use(express.json());
app.use(express.static("public"));


// MongoDB connection
const client = new MongoClient(process.env.MONGODB_URI, {
    family: 4
});


let studentsCollection;


// Connect to MongoDB
async function connectDB() {

    try {

        await client.connect();

        const db = client.db("collegeDB");

        studentsCollection = db.collection("students");

        console.log("Connected to MongoDB Atlas");

        // Start server only after MongoDB connection
        app.listen(PORT, () => {
            console.log(`Server running at http://localhost:${PORT}`);
        });

    } catch (error) {

        console.error("MongoDB connection error:", error);

    }
}


connectDB();



// ========================================
// CREATE - Add Student
// ========================================


app.post("/students", async (req, res) => {

    try {

        const student = req.body;

        const result =
            await studentsCollection.insertOne(student);

        res.json({

            message: "Student added successfully",
            id: result.insertedId

        });

    } catch (error) {

        res.status(500).json({

            error: error.message

        });

    }

});



// ========================================
// READ - Get All Students
// ========================================


app.get("/students", async (req, res) => {

    try {

        const students =
            await studentsCollection.find().toArray();

        res.json(students);

    } catch (error) {

        res.status(500).json({

            error: error.message

        });

    }

});



// ========================================
// DELETE - Delete Student
// ========================================


app.delete("/students/:id", async (req, res) => {

    try {

        const id = req.params.id;

        const result =
            await studentsCollection.deleteOne({

                _id: new ObjectId(id)

            });

        res.json({

            message: "Student deleted successfully",
            deletedCount: result.deletedCount

        });

    } catch (error) {

        res.status(500).json({

            error: error.message

        });

    }

});
```

### Frontend: public/index.html

```html
<!DOCTYPE html>
<html>

<head>

    <title>Student Management System</title>

    <style>

        body {
            font-family: Arial, sans-serif;
            margin: 40px;
        }

        h1 {
            color: #333;
        }

        input {
            padding: 10px;
            margin: 5px;
            width: 200px;
        }

        button {
            padding: 10px 15px;
            margin: 5px;
            cursor: pointer;
        }

        table {
            border-collapse: collapse;
            width: 80%;
            margin-top: 30px;
        }

        th, td {
            border: 1px solid #999;
            padding: 10px;
            text-align: left;
        }

        th {
            background-color: #eee;
        }

    </style>

</head>


<body>

    <h1>Student Management System</h1>

    <h2>Add Student</h2>

    <input
        type="text"
        id="name"
        placeholder="Student Name"
    >

    <input
        type="text"
        id="rollNo"
        placeholder="Roll Number"
    >

    <input
        type="text"
        id="course"
        placeholder="Course"
    >

    <button onclick="addStudent()">
        Add Student
    </button>


    <h2>Student List</h2>

    <button onclick="getStudents()">
        Refresh Students
    </button>


    <table>

        <thead>

            <tr>

                <th>Name</th>

                <th>Roll Number</th>

                <th>Course</th>

                <th>Action</th>

            </tr>

        </thead>


        <tbody id="studentTable">

        </tbody>

    </table>

    <script>

        // ====================================
        // CREATE
        // ====================================

        async function addStudent() {

            const name =
                document.getElementById("name").value;

            const rollNo =
                document.getElementById("rollNo").value;

            const course =
                document.getElementById("course").value;


            const student = {
                name: name,
                rollNo: rollNo,
                course: course

            };


            const response = await fetch("/students", {

                method: "POST",

                headers: {

                    "Content-Type": "application/json"

                },

                body: JSON.stringify(student)

            });


            const result = await response.json();

            alert(result.message);

            document.getElementById("name").value = "";

            document.getElementById("rollNo").value = "";

            document.getElementById("course").value = "";

            getStudents();

        }

        // ====================================
        // READ
        // ====================================

        async function getStudents() {

            const response =
                await fetch("/students");

            const students =
                await response.json();

            const table =
                document.getElementById("studentTable");

            table.innerHTML = "";
            students.forEach(student => {

                const row = `

                    <tr>

                        <td>
                            ${student.name}
                        </td>

                        <td>
                            ${student.rollNo}
                        </td>

                        <td>
                            ${student.course}
                        </td>

                        <td>

                            <button
onclick="deleteStudent('${student._id}')"> Delete </button>
                        </td>

                    </tr>

                `;
                table.innerHTML += row;

            });

        }


        // ====================================
        // DELETE
        // ====================================

        async function deleteStudent(id) {

            const response =
                await fetch(`/students/${id}`, {

                    method: "DELETE"

                });


            const result =
                await response.json();


            alert(result.message);


            getStudents();

        }

    </script>

</body>

</html>
```

> The CSS here was already short, so it is kept as it was.

### Common errors

| Error | Cause | Fix |
|---|---|---|
| `TypeError: The "uri" argument must be of type string. Received undefined` (or similar) | `process.env.MONGODB_URI` is empty | The file must be named exactly `.env` and sit in the project root. The variable name must be `MONGODB_URI`. No spaces or quotes. Restart `node server.js`. |
| `MongoServerSelectionError: ... IP that isn't whitelisted` / `Could not connect to any servers` | Your current IP is not in Atlas Network Access | Atlas → **Network Access** → add your current IP (wait for **Active**). Re-add it after changing Wi-Fi/hotspot. |
| `MongoServerError: bad auth : Authentication failed` | Wrong username/password, or `<password>` brackets left in | Check **Database Access**. Re-type the password in `.env`. If the password has `@ : / ? #`, change it to a simpler one or URL-encode it (`@` → `%40`). |
| `querySrv ECONNREFUSED _mongodb._tcp.cluster0...` / `ENOTFOUND` | DNS problem on the network (this is why `family: 4` is in your code) | Switch to a mobile hotspot, or set DNS to `8.8.8.8` / `8.8.4.4` in your network adapter, or use the non-SRV (standard) connection string from Atlas. |
| Browser shows `Cannot GET /` | `index.html` is missing or not inside `public` | Create `public/index.html` (folder named exactly `public`). |
| `Cannot find module 'express'` (or `mongodb`, `dotenv`) | Packages not installed | Run `npm install express mongodb dotenv` in `Wad_ass11`. |
| Table does not update | Server stopped, or you opened `index.html` by double-clicking | Always open <http://localhost:3000> (served by Express), not the file directly. |
| `BSONError: input must be a 24 character hex string` (on delete) | Invalid id passed to `ObjectId` | Delete using the button in the table, so the real `_id` is passed. |
| `EADDRINUSE: 3000` | Old server still running | `Ctrl + C` or `taskkill /F /IM node.exe`. |

---

## Experiment 12: Git, GitHub, Jenkins and Apache Tomcat

**Aim:** To understand the use of Git, Jenkins and Apache Tomcat for managing and running a web application.

### Downloads (one place)

| Tool | Download link | Notes |
|---|---|---|
| Git for Windows | <https://git-scm.com/download/win> | "Click here to download" (64-bit Setup) |
| GitHub account | <https://github.com/signup> | Free account |
| JDK (Java) | <https://adoptium.net/temurin/releases/> | Choose **Windows x64, .msi**, version **17** (or 21). Jenkins and Tomcat both need Java. |
| Jenkins | <https://www.jenkins.io/download/> | Choose **Long-Term Support (LTS) → Windows** |
| Apache Tomcat 9 | <https://tomcat.apache.org/download-90.cgi> | Under *Binary Distributions → Core* choose **64-bit Windows zip** |

### Part A: Install Java (JDK)

1. Download the JDK from the Adoptium link above and run the `.msi`.
2. On *Custom Setup*, enable **Set JAVA_HOME variable** and **Add to PATH**.
3. Open a **new** Command Prompt and verify:

```bash
java -version
```

### Part B: Install Git and use GitHub

1. Download and install Git from the link above (default options are fine).
2. Verify in a **new** Command Prompt:

```bash
git --version
```

3. One-time identity setup (use your own details):

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

4. On GitHub click **New repository** → name **MyWebApp** → **Public** → **Create repository** (do **not** add a README, so the repo starts empty). Copy the repository URL.

### Part C: Create, commit and upload the web application

1. Create a folder `MyWebApp` and inside it create `index.html` with a simple page (sample below; the exact page is not given in your journal).
2. Open Command Prompt **inside** `MyWebApp` and run (replace `YOUR_REPOSITORY_URL`, for example `https://github.com/<your-username>/MyWebApp.git`):

```bash
git init
git add .
git commit -m "Initial web application"
git remote add origin YOUR_REPOSITORY_URL
git branch -M main
git push -u origin main
```

3. **Clone** the repository into a different location (for example your Desktop):

```bash
git clone YOUR_REPOSITORY_URL
```

4. **Modify and update:** open `index.html` inside the cloned folder, change the heading, save, then run inside the cloned folder:

```bash
git add .
git commit -m "Updated application title"
git push
```

Sample `index.html`:

```html
<!DOCTYPE html>
<html>
<head>
    <title>MyWebApp</title>
</head>
<body>
    <h1>My Web Application</h1>
    <p>This page is deployed using Git, Jenkins and Apache Tomcat.</p>
</body>
</html>
```

### Part D: Install and configure Jenkins

1. Download the LTS Windows installer from <https://www.jenkins.io/download/> and run it.
2. On *Service Logon Credentials* choose **Run service as LocalSystem** (simplest for a lab PC).
3. On *Port Selection* keep **8080** and click **Test Port** (it should say the port is free).
4. On *Java home directory* select the folder of your JDK (for example `C:\Program Files\Eclipse Adoptium\jdk-17...`), then **Install**.
5. Open <http://localhost:8080> in the browser.
6. **Unlock Jenkins:** the page shows the path of the `initialAdminPassword` file (usually `C:\ProgramData\Jenkins\.jenkins\secrets\initialAdminPassword`). Open that file in Notepad, copy the password and paste it.
7. Choose **Install suggested plugins**, wait for it to finish, create the admin user, then **Save and Finish**.

**Create the job and fetch code from GitHub**

1. Click **New Item** → name **MyWebApp** → select **Freestyle project** → **OK**.
2. Under **Source Code Management** select **Git** and paste the repository URL (a **public** repo needs no credentials).
3. Set **Branch Specifier** to `*/main` (Jenkins defaults to `*/master`, which does not exist in your repo).
4. Click **Save**, then **Build Now**.
5. Open **Build History → #1 → Console Output**. It should end with `Finished: SUCCESS` after fetching the code from GitHub.

### Part E: Install Apache Tomcat and deploy the application

1. Download the **64-bit Windows zip** from the Tomcat 9 link above.
2. Extract it so that the folder is `C:\Tomcat` and it directly contains `bin`, `conf` and `webapps`.
   (If you get `C:\Tomcat\apache-tomcat-9.x.x\bin`, move the contents one level up.)
3. **Change the port from 8080 to 8081** (Jenkins already uses 8080).
   - Open `C:\Tomcat\conf\server.xml` in Notepad.
   - Find the HTTP connector and change the port:

```xml
<Connector port="8081" protocol="HTTP/1.1"
           connectionTimeout="20000"
           redirectPort="8443" />
```

4. **Start Tomcat:** open Command Prompt, then:

```bash
cd C:\Tomcat\bin
startup.bat
```

   A new Tomcat window opens. Keep it open.
5. Open <http://localhost:8081> and check that the Tomcat welcome page appears.
6. **Deploy:** create the folder `C:\Tomcat\webapps\MyWebApp` and copy `index.html` into it.
7. Open <http://localhost:8081/MyWebApp/> in Chrome. The page should be displayed.
8. To stop Tomcat: run `shutdown.bat` in the same `bin` folder.

> **Journal check:** your Procedure uses `http://localhost:8081/MyWebApp/` but your Output section says `/WebApp/`. The URL must match the folder name inside `webapps`, so make the Output line say `/MyWebApp/` (or rename the folder to `WebApp`).

### Common errors

| Tool | Error | Cause | Fix |
|---|---|---|---|
| Git | `'git' is not recognized` | Terminal opened before install | Open a new Command Prompt; reinstall Git if needed. |
| Git | `Author identity unknown` / `Please tell me who you are` | Name and email not set | Run the two `git config --global` commands in Part B. |
| Git | `fatal: not a git repository` | Command run in the wrong folder | `cd` into the folder that contains the `.git` folder. |
| Git | `error: remote origin already exists` | Remote was added before | `git remote set-url origin YOUR_REPOSITORY_URL` |
| Git | `src refspec main does not match any` | No commit yet, or branch is not `main` | Run `git add .` and `git commit -m "..."` first, then `git branch -M main`. |
| Git | `failed to push some refs` / `fetch first` | GitHub repo was created with a README | `git pull origin main --allow-unrelated-histories`, then `git push`. Or create an empty repo. |
| Git | `Authentication failed` / password rejected | GitHub no longer accepts account passwords for Git | Sign in through the browser window Git opens (Git Credential Manager), or use a **Personal Access Token** (<https://github.com/settings/tokens>) as the password. |
| Java | `'java' is not recognized` | JDK not installed or not on PATH | Reinstall the JDK with *Add to PATH* and *Set JAVA_HOME* enabled; open a new terminal. |
| Jenkins | Jenkins page does not open / `ERR_CONNECTION_REFUSED` | Jenkins service not running | `Win + R` → `services.msc` → **Jenkins** → **Start**. Wait 1 to 2 minutes after starting. |
| Jenkins | Port 8080 already in use | Another app (often Tomcat) uses 8080 | Keep Tomcat on 8081. Stop other apps using 8080, or choose another Jenkins port during install. |
| Jenkins | Installer says Java not found or unsupported version | Wrong or missing JDK | Install JDK 17 or 21 and point the installer to it. Check supported versions at <https://www.jenkins.io/doc/administration/requirements/java/>. |
| Jenkins | `Couldn't find any revision to build` / `couldn't find remote ref refs/heads/master` | Branch specifier is `*/master` | Change **Branch Specifier** to `*/main` in the job configuration. |
| Jenkins | `Failed to connect to repository` / `Cannot run program "git"` | Git missing for Jenkins, or the repo is private | Install Git, then restart the Jenkins service. Use a **public** repo (or add credentials). |
| Tomcat | Window flashes and closes; `The JAVA_HOME environment variable is not defined correctly` | `JAVA_HOME` not set | Win → "Edit the system environment variables" → **New** system variable `JAVA_HOME` = your JDK folder (for example `C:\Program Files\Eclipse Adoptium\jdk-17...`). Open a new Command Prompt and run `startup.bat` again. |
| Tomcat | `Address already in use: 8080` or `8081` | Port clash | Change the Connector port in `server.xml`, or stop the program using it (`netstat -ano \| findstr 8081`). |
| Tomcat | `localhost:8081` does not open | Tomcat not started, or the port edit was not saved | Check that the Tomcat window is open with no errors. Re-check `server.xml` and restart with `shutdown.bat` then `startup.bat`. |
| Tomcat | `HTTP 404` on `/MyWebApp/` | Folder name, location or case is wrong | `index.html` must be in `C:\Tomcat\webapps\MyWebApp\` and the URL must use the same name and case. |

---

### Quick reference: default ports used in these experiments

| Service | Port |
|---|---|
| Node.js apps (Exp 7, 8, 11) | 3000 |
| MongoDB local server (Exp 9, 10) | 27017 |
| Jenkins | 8080 |
| Apache Tomcat (changed from 8080) | 8081 |
