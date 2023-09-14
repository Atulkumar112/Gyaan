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








