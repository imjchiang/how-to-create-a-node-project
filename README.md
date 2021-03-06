# How to Create a Node Project

1. create a new directory
    - ```mkdir new-directory```
2. change into that directory
    - ```cd new-directory```
3. initialize node
    - ```npm init```
4. press enter if going to use defaults and okay it
5. create an index.js or whatever the entry file is supposed to be called
    - ```touch index.js```

### Making your own module
6. create a JS file that will contain your node module
    - ```touch myModule.js```
7. add your node module function
    - ```module.exports.coolFunction = () => {/*insert cool function here*/}```

### Running your module function
8. import it to your main/entry file
    - ```const myModule = require("./myModule.js");```
9. run the node module function you made
    - ```console.log(myModule.coolFunction());```

### Installing an npm package
10. find npm package and install it
    - ```npm i thisIsMyPackage```
    - ```npm i -g thisIsAGlobalInstall```

### Implementing the package
11. import the package
    - ```const newPackage = require("thisIsMyPackage");```
12. run the different functions of the package
    - ```console.log(newPackage.packageFunction());```

### Adding a .gitignore
13. add a ```.gitignore``` file
    - ```touch .gitignore```
14. add text to help ignore package folders and content
    - ```node_modules```

### Adding express to a node app
15. install express
    - ```npm i express```
16. initialize express in ```index.js```
    - ```const express = require("express");```
17. initialize the app in ```index.js```
    - ```const app = express();```

### Express routes
18. add a listener for the specific local port you want
    - ```app.listen(8000, function() {console.log("Listening to port 8000");});```
19. initialize the home page
    ```javascript
    app.get("/", function(req, res)
    {
        res.send("This is the home page");
    });
    ```
20. add on other pages with other paths
    ```javascript
    app.get("/animals", function(req, res)
    {
        res.send("This is a page about animals");
    });
    ```

### Views
21. create views folder in main directory
    - ```mkdir views```
22. create boilerplate html files in views directory
    - ```touch views/index.html```
23. insert whatever content you want in the html files
24. change method of sending files in index.js
    - ```res.sendFile(__dirname + "/views/index.html");```

### Templates
25. install ejs
    - ```npm i ejs```
26. use ejs as view engine
    - ```app.set("view engine", "ejs");```
27. change html files in views to ejs type
28. use render instead of sendFile
    - ```res.render("index");```
29. OPTIONAL: add variables to be implemented in your ejs document through the calling of render
    - ```res.render("index", {name: "potatoes", num: 35});```
    - ```<h1>You have <%= num %> <%= name %> in your salad!</h1>```

### Layouts
30. install express-ejs-layouts
    - ```npm i express-ejs-layouts```
31. set up ejs layouts
    - ```const ejsLayouts = require("express-ejs-layouts");```
    - ```app.use(ejsLayouts);```
32. create a layout.ejs in views directory
    - ```touch views/layout.ejs```
33. set up layout.ejs: add <%- body %> tag in body
    - ```<%- body %>```
34. create a home.ejs in views directory
    - ```touch views/home.ejs```
35. create home route in index.js
    ```javascript
    app.get("/", function(req, res) 
    {
        res.render("home");
    });
    ```
36. add other routes in index.js
    ```javascript
    app.get("/animals", function(req, res) 
    {
        res.render("animals", {title: "Favorite Animals", animals: ["sand crab", "corny joke dog"]})
    });
    ```
37. OPTIONAL: add navigation in layout.ejs
    ```javascript
    <ul>
        <li><a href='/foods'>Favorite Foods</a></li>
        <li><a href='/animals'>Favorite Animals</a></li>
    </ul>
    <%- body %>
    ```

### Controllers
38. create a controllers folder in your root directory
    - ```mkdir controllers```
39. place all your routes besides your home route in the controller folder
40. set up express and the router in the file containing the other routes in the controllers folder
    ```javascript
    const express = require("express");
    const router = express.Router();

    ...

    module.exports = router;
    ```
41. use router for the routes that are in controller files
    ```javascript
    router.get("/foods", function(req, res)
    {
        res.render("faves/foods", {title: "Favorite Foods", foods: ["potatoes", "yams", "steak"]});
    });
    ```
42. go back to the entry file and add middleware for routes
    - ```app.use('/faves', require('./controllers/faves'));```




createdb -U imjchiang pokedex

sequelize model:create --name pokemon --attributes name:string

sequelize db:migrate