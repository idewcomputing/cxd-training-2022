# Programming Warm-Up ⏱

## **The Big Picture**

{% embed url="https://www.loom.com/share/ce345dac33cd401786605cea6c9a2438" %}

**A program can be defined simply as **_**a set of instructions that perform defined tasks,**_ and we can use the  diagram below to frame the major components of a program. A program can be written to accept particular _**inputs,**_ like a mouse click, sound from a microphone, or a reading from a temperature sensor. The same program can handle the storage and retrieval of _**data**_, like _to do_ items or historical temperature data. The same program can then **output** something useful, like a current _to do_ list or move robot wheels. Multiple _**functions**_ are written to control and process everything towards some useful end, each function handling a particular task.

![](<../../.gitbook/assets/image (6) (1).png>)

{% hint style="success" %}
**Consider planning an in-class activity where students diagram a computing application** (whether a social app, an AI driven tractor, or a video game console). Have them consider what inputs, data, and outputs the program includes. While the students will not know exactly how the engineers designed the application, they can come up with some specific function names to guess how the application processes the information. For example, a phone may have a **function** called "changeScreenBrightness" that takes the light sensor **input** to update the screen's brightness (**output**) based on a stored user preference (**data**).
{% endhint %}

#### Programming Languages

This exercise will use **JavaScript**, the primary programming language for web applications that work in a standard browser. There are many other popular programming languages. A particular language is chosen for implementation based on several factors related to the context of the need. Here are a few you may have heard of -- **Python, Java (different from JavaScript!), Arduino, C++ and C#**.  Note: While HTML and CSS are languages with a defined syntax, they are usually distinguished from programming languages that provide computation and functions.

## Let's Program: Variables, Functions, Conditionals, and Objects

This exercise takes a direct approach to prepare you for programming a CxD project by taking an _"application first"_ perspective. **We will frame this introduction by creating a simplified **_**To Do Application**_** using Javascript.**&#x20;

{% hint style="info" %}
**You are highly encouraged to build (and experiment with) the program as demonstrated in the video to get a feel for the programming.**  Also, remember to also try some online tutorials as a supplemental experience as explained in the _Workshop Prep_.
{% endhint %}

{% embed url="https://www.loom.com/share/22275f0694664a15acbe635c298e6b1a" %}

### Declare Variables and Use a Built-in Function

First, in our _script.js_ file, let's **declare** some **variables** of different **data types** and set their **values**.

* &#x20;`todo` is a _**string**_
* &#x20;`time` is a _**number**_
* &#x20;`isComplete` is a _**boolean**_ (true or false).&#x20;

Then we use a **built-in function** `console.log()` to display the values.

{% code title="script.js" %}
```javascript
//declare some variables for our data
var todo = "Walk the dog.";
var time = 30;
var isComplete = false;

//use a built-in function `console.log()` to output values
console.log(todo); 
console.log(time);
console.log(isComplete);
```
{% endcode %}

### Define a Custom Function

Here we **define** a **custom function** `displayTodos()`. This allows us to **call** (or **invoke**) the function whenever we want.

{% code title="script.js" %}
```javascript
//declare some variables for our data
var todo = "Walk the dog.";
var time = 30;
var isComplete = false;

//define a custom function to output to do's
function displayTodos() {
  console.log(todo);
  console.log(time);
  console.log(isComplete);
}

//call (or invoke) the displayTodos() function to actually run it
displayTodos();
```
{% endcode %}

### Use a Conditional Statement

Here we use a **conditional statement** (using **if/else**) _****_ to customize the output.

{% code title="script.js" %}
```javascript
//declare some variables for our data
var todo = "Walk the dog.";
var time = 30;
var isComplete = false;

//define a custom function to output to do's
function displayTodos() {
  console.log(todo);
  console.log(time);
  
  //customize the output based on whether it is complete
  if (isComplete) {
    console.log("This is complete.");
  }
  else {
    console.log("This is not complete");
  }
}

//call (or invoke) the displayTodos() function to actually run it
displayTodos();
```
{% endcode %}

### Use an Object

Here we will use a single **object** variable to hold all the data for a particular to-do item.

{% code title="script.js" %}
```javascript
//declare a variable for our data
var todo = {
  text: "Walk the dog.",
  time: 30,
  isComplete: false
};

//define a custom function to output to do's
function displayTodos() {
  console.log(todo.text);
  console.log(todo.time);
  
  //customize the output based on whether it is complete
  if (todo.isComplete) {
    console.log("This is complete.");
  }
  else {
    console.log("This is not complete");
  }
}

//call (or invoke) the displayTodos() function to actually run it
displayTodos();
```
{% endcode %}

## JavaScript Arrays

{% embed url="https://www.loom.com/share/095f0e88058b49aaa4016d8d1a24c648" %}

### Make a List (or Array)

Here we will use an **array** and **for-loop** to list multiple to-do items. We will ignore the time and completion data for now.

{% code title="script.js" %}
```javascript
//declare a variable
var todos = ["Walk the dog.","Go to grocery.","Call mom."];

//define a custom function to display to do's
function displayTodos() {
  todos.forEach(function(todo) {
    console.log(todo);
  })
}

//call (or invoke) the displayTodos() function to actually run it
displayTodos();
```
{% endcode %}

### Make an Array of Objects

Here we will combine our use of an **array** with **objects**. **This is the most difficult concept of this exercise and may take some time to digest. But it demonstrates a lot of powerful programming concepts in a very small program. 🚀🚀🚀🚀**

{% code title="script.js" %}
```javascript
//declare a variable
var todos = [
  {
    text: "Walk the dog.",
    time: 30
  },
  {
    text: "Go to grocery.",
    time: 60
  },
];

//define a custom function to display to do's
function displayTodos() {
  todos.forEach(function (todo) {
    console.log("---");
    console.log(todo.text);
    console.log(todo.time + " minutes");
  })
}

//call (or invoke) the displayTodos() function to actually run it
displayTodos();
```
{% endcode %}

{% hint style="success" %}
#### 🎉Congratulations for making it through so many programming concepts in a short time! &#x20;
{% endhint %}

## Wrap-Up

That's our warm-up. Whether you found these concepts incredibly difficult or mostly review, please don't hesitate posting questions along with a link to your replit code in our Slack channel for the workshop.
