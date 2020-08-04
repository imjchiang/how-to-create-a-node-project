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
