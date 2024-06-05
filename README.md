.htm [SPOILER=htm]
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8"> 
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Simple website</title>
  <link rel="stylesheet" href="../main.css">
</head>
<body class="light-theme">
    <h1>Task list</h1>
    <p id="msg">Current tasks:</p>
    <ul>
        <li class="list">Add new visual styles</li>
        <li class="list">Add light and dark themes</li>
        <li>Enable switching the theme</li>

    </ul>
    <div><button class="btn">Dark</button></div>
</body>
<script src="../app.js"></script>
</html>
[/SPOILER]
[SPOILER=css]
,
:root {
    --green: #00FF00;
    --white: #FFFFFF;
    --black: #000000;
  }
  body {
    background: var(--bg);
    color: var(--fontColor);
    font-family: helvetica;
  }
ul {font-family: Helvetica; } 
li {
    list-style: circle;
  }
  .list {
    list-style: square;
  }
  .light-theme {
    --bg: var(--green);
    --fontColor: var(--black);
    --btnBg: var(--black);
    --btnFontColor: var(--white);
  }
  
  .dark-theme {
    --bg: var(--black);
    --fontColor: var(--green);
    --btnBg: var(--white);
    --btnFontColor: var(--black);
  }
  .btn {
    position: absolute;
    top: 20px;
    left: 250px;
    height: 50px;
    width: 50px;
    border-radius: 50%;
    border: none;
    color: var(--btnFontColor);
    background-color: var(--btnBg);
  }
[/SPOILER]
[SPOILER=jss]
'use strict';

const switcher = document.querySelector('.btn');

switcher.addEventListener('click', function() {
    document.body.classList.toggle('light-theme');
    document.body.classList.toggle('dark-theme');

    const className = document.body.className;
    if(className == "light-theme") {
        this.textContent = "Dark";
    } else {
        this.textContent = "Light";
    }

    console.log('current class name: ' + className);
});
[/SPOILER]

