---
tags:
  - Blogs
---
Browser is an application that runs on top of your operating system used to surf the web. It is very complex as it is able to utilize your computer system hardware to run complex web application and even games. It not only displays the webpages but also handle use interactions, run various scripts, manage security and communicate with web servers. They act as an interface between the user and the internet.

**Main Parts of a browser**
- User Interface (UI) : With the use of ui you interact with the browser. This includes the address bar, back/ forward buttons, tabs .. etc
- Browser Engine: It is the coordinator between the UI and the render engine. It ensures whatever is rendered by the render engine is displayed by the ui
- Render Engine: Converts HTML, CSS and JavaScript into visual and interactive elements in the screen
- Networking: Fetches resources either using HTTP or HTTPS
- JavaScript Engine: Executes JavaScript logics in the page
- Data Storage: Stores cache, keys, token and passwords

**Browser Engine vs Render Engine**
The browser engine acts as a bridge between the UI and the Render Engine whereas the Render Engine is responsive for doing all the calculations on how the website should look, what should happen after you press a button, calculations for the animations and visuals you see in the web-apps. Now a days render engine takes advantage of gpu acceleration to make animation and rendering a lot more efficient and fast.

**Real world example of how a browser works**
- You write facebook.com on the address bar and press enter
- Browser resolves the domain using DNS
- Fetches the resources from the ip address that the authoritative DNS provider gave
- Parses the HTML into the DOM (Document Object Model)
- Parses CSS into the CSSOM (CSS Object Model)
- Combines DOM and CSSOM into the **render tree**
- Preform layout calculations and displays the webpage
- Executes JavaScript Using the javascript Engine to handle user interactions
