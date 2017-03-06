# Reflection exercise

Concept:

## - Variables, arrays, objects:

  * Variables are like containers to store data/information in.

  Declair a varbiable with var / let / const. The variable needs to be given a name so you can uses it. The data kan be a array, object, function, Boolean, string

``` javascript
  var "name" = "data"  
  var welcome = "Welcome Wijnand"
  var number = 10
```  
  * Objects are a collection of properties, and a property is an association between a name (or key) and a value. A property's value can be a function, in which case the property is known as a method. In addition to objects that are predefined in the browser, you can define your own objects.



``` javascript
  var person = {
    firstName:"John",
    lastName:"Doe",
    age:50,
    eyeColor:"blue"

  //you can acces the value of a property bij calling it with the key.

  objectName.propertyName
  person.firstname // is value "John"
};
```

  * A array is a type of object to store multiple values in.

  think of a array as a list. Its common to store data that is of the same tipe. Look at it like a shoppinglist. In the shoppinglist u write the groceries in the list you want to buy.
  Make a variable and use the square brackets [] to declaire a array
``` javascript
  var "name" = ["name" "name" "etc"]
  var thisArrayShoppinglist = ["apples", "Cake", "cookies", "wine"]
```

## - Functions

 * A function is a mini programme you code/write to do someting for u. Usually a function is named so you can use it elsewhere in your code by calling it.

 A function can have paramaters to pas information to that can be used in the function.

 ``` javascript
function myFunction(x) {
    return x * x
    console.log(x) // outcome is 25
}

 myFunction(5);
```


## - Iteration loops (for and while)

  * with loops you can do somting multiple time by setting the right paramaters.

  A for loop repeats until a specified condition is no longer true. A wile loop runs until a condition is met.

``` javascript
var beer;
for (beer = 0; beer < 10; beer++) {
  // Runs 10 times, with values from 0 to 9.
  console.log('I just ordered a round of beers :)');
}
```


## - Anonymous callback functions
  a function without a name. Moostly these are auto invoking and run only one time. Exception is when the function is set on a variable.

``` javascript
  // anonymous function in a variable
  var x = function (a, b) {return a * b};
  var z = x(4, 3);

  // anonymous auto  invoking function
  (function () {
    var x = "Hello!!";      
})();
```

## - Promises

  * A promise is a method that eventually produces a value.

  It can be considered as the asynchronous counterpart of a getter function. A promise can have three states: pending, fulfilled, or rejected. The outcome can be passed to.

``` javascript
  promise.then(function(value) {
  // Do something with the 'value'

  function dieToss() {
  return Math.floor(Math.random() * 6) + 1;
}

console.log('1');
var promise = new RSVP.Promise(function(fulfill, reject) {
  var n = dieToss();
  if (n === 6) {
    fulfill(n);
  } else {
    reject(n);
  }
  console.log('2');
});

promise.then(function(toss) {
  console.log('Yay, threw a ' + toss + '.');  
}, function(toss) {
  console.log('Oh, noes, threw a ' + toss + '.');  
});
console.log('3');
});
```


## - File system module

  * the file system mudule makes it possible to do all kinds of things with file, but moostly its used to read an write files. Its a module used in the backend.

``` javascript
//the file system needs to be required:
var file = require('file-system');
var fs = require('fs');

//to write to the file test.txt
fs.writeFile('path/test.txt', 'aaa', function(err) {})

//to read a file passwd
fs.readFile('/etc/passwd', (err, data) => {
  if (err) throw err;
  console.log(data);
});
```


## - Express

  * Express is used to setup a server with node.

  express needs to be installed befor it can be used. Alse it needs te be required in javascript. With express there can be interaction between the frontend and the backend.

  ``` javascript
  /// requiring express in JS
  var express = require('express')
  var app = express()

  // GET method route
  app.get('/', function (req, res) {
    res.send('GET request to the homepage')
  })
  });

  // POST method route
  app.post('/', function (req, res) {
    res.send('POST request to the homepage')
  })
  });
    // setting a route
    app.route('/book')
    .get(function (req, res) {
      res.send('Get a random book')
    })

    // middleware that is specific to this router
    router.use(function timeLog (req, res, next) {
      console.log('Time: ', Date.now())
      next()
    })

    // setting a route
    app.route('/book')
    .get(function (req, res) {
      res.send('Get a random book')
    })

    // middleware that is specific to this router
    router.use(function timeLog (req, res, next) {
      console.log('Time: ', Date.now())
      next()
    })

  ```


## - Body parser
  * body-parser is a module is used by node. it parses the HTTP request body. This is usually necessary when you need to know more than just the URL being hit, more specifically in the context of a POST, PATCH or PUT HTTP request where the information you want is contained in the body.

  Using body parser allows you to access req.body from within your routes, and use that data for example to create a user in a database. In our case we moostly used it with JSON to read and write the file.



## - html markup


## - jQuery

  * is a library for javascript moostly used to make it easer to manipulate the frond and and make it do things.

  For example change text when a action on the site is preformed .


## - Pug (discuss syntax and variables)
  Pug is a view engine to render HTML form the backend. Also in pug you can use javascript objects.

## - AJAX
  Ajax is a node module with enabels you to render information in de body of a page without refreshing it

## - Cookies
  * are delicious and can be stored on the computer of a user to store stuff and gather information.

  its possible to set Cookies form the backend, but its more common to set them from the frontend. Because the cookie is store on the user machine its not recommended to store sensitife information in it. To use cookies you need to install a module first and require the module in your application.

  ``` javascript
  //requiring the cookie module
  var cookie = require('cookie');

  //set a cookie
  var setCookie = cookie.serialize('foo', 'bar');
  ```

## - Sequelize ORM
  * Sequelize is a promise-based ORM(Object Relational Mapping) for Node.js. It supports PostgreSQL, MySQL, MariaDB, SQLite and MSSQL and features solid transaction support, relations, read replication and more.

  With Sequelize U are able to make tables in the databese and store information

  ``` javascript
  var Sequelize = require('sequelize');
  var sequelize = new Sequelize('database', 'username', 'password');

var User = sequelize.define('user', {
  username: Sequelize.STRING,
  birthday: Sequelize.DATE
});

sequelize.sync().then(function() {
  return User.create({
    username: 'janedoe',
    birthday: new Date(1980, 6, 20)
  });
}).then(function(jane) {
  console.log(jane.get({
    plain: true
  }));
});
```
