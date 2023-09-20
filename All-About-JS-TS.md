# JavaScript/TypeScript 😀

### prompt() method 
This is similer to alert function but it takes input from user in our pop up window it's use to take the input from user.

### console.table
```bash
const obj = {a: 1, b: 2, c: 3};
console.table(obj) // the outpt should be in table form. just run it in console and see.
```
### Searching Logic using RegEx
```bash
 if (query === '') {
    result = allSpacecrafts.value
  } else {
    result = allSpacecrafts.value.filter((s) =>
      (
        (s?.name ?? '').replace(/[^A-Za-z]/g, '').toLowerCase() + s.noradCatId
      ).includes(query)
    )
  }
 ```
 
 ### Add CSS class
You can add any css class using javascript.
```bash
 idName.classList.add("thisIsMyClassName");
 ```
Using `.toggle()`, if id already have class then it will remove it and if id have not this class then it will add it. 
```bash
idName.classList.toggle("thisIsMyClassName") 
 ```
 
## SetTimeout and SetInterval
 
 ### SetTimeOut
 when i want to execute our js code after a certain time of period then we use setTimeout function. 
 - Ex:- show some popup on your website after 2-3 second of loading you website landing page.
 
### SetInterval
when you want to run you js code again and again for the certain time or until you will not stop it. 
- Ex:- if you want to get the data from you Api endpoint but it can take 20 second to 60 second to get the data (also based upon the internet) then we use it and we will check again and again like we got data or not. if we not get data then continue our timeInterval and if we got data then stop you interval.
 
 ## Diff between addEventListener and onClick() Event
 
 ### addEventListener
The addEventListener() method can have multiple event handlers applied to the same element. It doesn’t overwrite other event handlers. it's takes 3 parameters first is event name, second is task/function name, last one is useCapture which is optional.
1. event: Event can be any valid JavaScript event. Events are used without the “on” prefix like use “click” instead of “onclick” or “mousedown” instead of “onmousedown”.
2. listener(handler function): It can be a JavaScript function that responds to the event that occurs.
3. useCapture:  (Optional parameter) A Boolean value that specifies whether the event should be executed in the capturing or in the bubbling phase.

Example:- 
```bash
<body>
<button id="btn">Click here</button>
<h1 id="text1"></h1>
<h1 id="text2"></h1>                                                            //output
										when you click on the button both heading will appears
<script>
	let btn_element = document.getElementById("btn");			so the output is:
										text1
	btn_element.addEventListener("click", () => {				text2
	document.getElementById("text1")
		.innerHTML = "Task 1 is performed";
	})

	btn_element.addEventListener("click", () => {
	document.getElementById("text2")
		.innerHTML = "Task 2 is performed";
	});
</script>
</body>

// Output
text1
text2
// when you click on the button both heading will appears
```

### onClick event
The onclick event logs the click activity, and then calls a desired function, the onClick event only adds one event to an element.
if we try to write more than one property/event funtion, then it will be overwritten.

Example:-  
```bash
<body>
<button id="btn">Click here</button>
<h1 id="text1"></h1>                                                            
<h1 id="text2"></h1>								
																
<script>									
	let btn_element = document.getElementById("btn");

	btn_element.onclick = () => {
	document.getElementById("text1")
		.innerHTML = "Task 1 is performed";
	};

	btn_element.onclick = () => {
	document.getElementById("text2")
		.innerHTML = "Task 2 is performed";
	};
</script>
</body>

//Output
text2
//it will be overwrite first event from the second one.
```

## Synchronous & Asynchronous Methods
- Synchronous actions are the actions that initiate and finish one-by-one. Ex:- if we write multiple console.log(), those console run one by one.

- Asynchronous actions are those actions when we initiate now and they finish later. Ex:- setTimeout.

### Callback function

A callback function is a function passed into another function as an argument, which is then invoked inside the outer function to complete some kind of routine or action. Callback function can be a Synchronous or Asynchronous.

```bash
// function
function greet(name, callback) {
    console.log('Hi' + ' ' + name);
    callback();
}

// callback function
function callMe() {
    console.log('I am callback function');
}

// passing function as an argument
greet('Peter', callMe);

// Output
Hi Peter
I am callback function

```

## Promises
Promise is nothing but it's the parallel execution of an asynchronous operation.

A Promise is in one of these states:

- pending: initial state, neither fulfilled nor rejected.
- fulfilled: meaning that the operation was completed successfully.
- rejected: meaning that the operation failed.

Example:-
```bash
let promise = new Promise((resolve, reject) => {
        console.log("Promise is pending")
        setTimeout(() => {
                console.log("I am a promise and I am resolved")
                resolve("hi, i am fulfilled")
                // console.log("I am a promise and I am rejected")
                // reject(new Error("I am an error"))
        }, 3000)
})

promise.then((value)=>{
        console.log(value) 
},(error)=>{
        console.error(error)
})

```

### Promises chaining
We can chain promises and make them pass the resolved value to one another. i.e,

```bash
new Promise(function(resolve, reject) {

  setTimeout(() => resolve(1), 1000); // (*)

}).then(function(result) { // (**)

  alert(result); // 1
  return result * 2;

}).then(function(result) { // (***)

  alert(result); // 2
  return result * 2;

}).then(function(result) {

  alert(result); // 4
  return result * 2;

}).then((result) => {
    alert(result)
    console.log("all done")
});
```
- Promises chaining this is the solution of callback hell.

### Promises API
There are 6 static method of promise class:
1. Promise.all(promises):- Waits for all promises to resolve and returns the array of their results. If any one fails, it becomes the error & all other results are ignored.

2. Promise.allSettled(promises):- Waits for the first promise to setle and returns their results as an arrayof objects with status and value.

3. Promise.race(promises):- Waits for the first promise to settle and its result/error becomes the outcome.

4. Promise.any(promises):- Waits for the first promise to fulfill (& not rejected), and its result becomes the outcome. Throws AffrefateError if all the promises are rejected.

5. Promise.resolve(promises):- Makes a resolved promise with the given value.

6. Promise.reject(promises):- Makes a rejected promise with the error.

Examples:

```bash
let p1 = new Promise((resolve, reject) => {
        setTimeout(() => {
                resolve("Value 1");
        }, 1000);
});

let p2 = new Promise((resolve, reject) => {
        setTimeout(() => {
                // resolve("Value 2");
                reject(new Error("Error"));
        }, 2000);
});

let p3 = new Promise((resolve, reject) => {
        setTimeout(() => {
                resolve("Value 3");
        }, 3000);
});


let promise_all = Promise.all([p1, p2, p3])
// let promise_all = Promise.allSettled([p1, p2, p3])
// let promise_all = Promise.race([p1, p2, p3])
// let promise_all = Promise.any([p1, p2, p3])
// let promise_all = Promise.resolve(6)
// let promise_all = Promise.reject(new Error("Hey"))
promise_all.then((value) => {
    console.log(value)
})

```
### Async/Await

There’s a special syntax to work with promises in a more comfortable fashion, called “async/await”. It’s surprisingly easy to understand and use.

### Async functions
Let’s start with the async keyword. It can be placed before a function, like this:

``` bash
async function f() {
  return 1;
}
```
The word “async” before a function means one simple thing: a function always returns a promise. Other values are wrapped in a resolved promise automatically.

###Await
The syntax:
``` bash
// works only inside async functions
let value = await promise;
```
The keyword await makes JavaScript wait until that promise settles and returns its result.

- Let’s emphasize: await literally suspends the function execution until the promise settles, and then resumes it with the promise result. That doesn’t cost any CPU resources, because the JavaScript engine can do other jobs in the meantime: execute other scripts, handle events, etc.

## Error handling,"try...catch"

No matter how great we are at programming, sometimes our scripts have errors. They may occur because of our mistakes, an unexpected user input, an erroneous server response, and for a thousand other reasons.

Usually, a script “dies” (immediately stops) in case of an error, printing it to console.

But there’s a syntax construct try...catch that allows us to “catch” errors so the script can, instead of dying, do something more reasonable.

The try...catch construct has two main blocks: try, and then catch:
```bash
try {

  // code...

} catch (err) {

  // error handling

}
```
- *inside the try block we can writes only synchronous methods.*

- *Error messages:-* err.name and err.message. just try youself

### final() Clause:

`final()` defines after the catch block. it will run at any cost, weather try throw error or run fine or catch run or not, but final will be run. 

### XMLHttpRequest
XMLHttpRequest (XHR) objects are used to interact with servers. You can retrieve data from a URL without having to do a full page refresh. This enables a Web page to update just part of a page without disrupting what the user is doing. XMLHttpRequest is used heavily in AJAX programming.
- AJAX: Asynchronous JavaScript and XML, or Ajax, is not a technology in itself, but rather an approach to using a number of existing technologies together, including HTML or XHTML, CSS, JavaScript, DOM, XML, XSLT, and most importantly the XMLHttpRequest object. When these technologies are combined in the Ajax model, web applications are able to make quick, incremental updates to the user interface without reloading the entire browser page. This makes the application faster and more responsive to user actions. Ajax's most appealing characteristic is its "asynchronous" nature, which means it can communicate with the server, exchange data, and update the page without having to refresh the page.

Although X in Ajax stands for XML, JSON is preferred because it is lighter in size and is written in JavaScript. Both JSON and XML are used for packaging information in the Ajax model.

## Using the Fetch API

JavaScript can send network requests to the server and load new information whenever it’s needed.

```bash
async function logMovies() {
  const response = await fetch("http://example.com/movies.json");  // this gives only status
  const movies = await response.json();     // then this gives data
  console.log(movies);
}

// Similarly we can do same thing using 2 times .then() , first .then() would be for status and second .then() would be for data.

```
[fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch)

### Cookies
Cookies are small strings of data stored directly in the browser as JSON format. In JS, document cookie provides access to cookies.
You can check, which website stored your cookies in you browser by this:-
```bash
alert(document.cookie);

// you can alos add anything in you cookie
document.cookie = "username = atulkumar9999"
```
- when we writes cookie then it's not touch previous cookies. it just add new one.

### Local Storage
The localStorage object allows you to save key/value pairs in the browser. Note The localStorage object stores data with no expiration date. The data is not deleted when the browser is closed, and are available for future sessions.

Examples:
```bash
localStorage.setItem("name", "atul");
localStorage.getItem("name");
localStorage.removeItem("name");
localStorage.clear();
```

### Session Storage
Session storage is also same like local storage. but the major diff is if we refresh our page or open same page in diff tab then all data will be vanish.

### Diff b/w cookie and localstorage 
1. Key differences between the three. Cookies can be set to expire after a certain amount of time or be deleted manually, while local and session storage can be cleared only by the user or through a script. 

2. Cookies are sent back to the server with every request, while local and session storage are not automatically sent to the server.

3. OR Cookies are smaller and send server information back with every HTTP request, while LocalStorage is larger and can hold information on the client side.

##Links

- [JavaScript](https://javascript.info/) 


