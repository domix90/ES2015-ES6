# ES2015-ES6
Getting up to speed with ES2015


Const and let is similar to var
--------------------------
When const
--------------------------
constant - once you create it you cannot change the value for instance value PI cannot be changed if set in const. You cannot reassing string, numbers, booleans, objects and arrays. 

Objects and arrays have methods and properties however that can be used to modify the const. 

Object literal 
Arrays

const days = ["Monday"];

If I use method days.push("Freitag") the string will be added to the array. 

const person = {first_person: "Dominik"};

If I use method on the object person.last_name = "Sosen"; I will not get any errors. -- MODIFYING 

If I try to reassing the value by using person.first_name = "x" I will not get an error. I would get an error if I tried 

person = {first_name: "Anna" }; -- OVERWRITING

CONST DOES NOT prevent complex objects like arrays from being modified. It prevents the value from being reassigned or overwritten! 

Working on arrays examples of code which will not throw an error: 

1. const days = ['Monday', 'Tuesday', 'Wednesday' ];
days.push ('Friday', 'Saturday');

2. names = [];
names[0] = "Dom";

names[1] = "Aga"; 

names[2] = "Marcin i Magda";

3. const list = ["Eggs", "Milk", "Potato"];
list.pop();

list.pop();

list.pop();

The below example will give me error cause I am trying to pass another value to a fuction with a pre-defined const

const taxRate = 8.5;
function calculateTax(cost, tax) {
  taxRate = tax;
  return (cost * taxRate) / 100;
}
console.log(calculateTax(100, 10));

--------------------------
When let
--------------------------
let should be used when I want to reassign a value. It works like var. 

const person = {
            first_name: "Andrew",
            role: "Teacher"
        }
    
        function personDescription(person) {
           let description = person.first_name;
            if(person.role) {
                description = description + " is a ";
                description = description + person.role;
            }
            console.log(description);
        }
    
        personDescription(person);

Let is particularly useful in for loops. You should mostly use let for "for loops" as a good practice. 

<button> Button 0 </button>
<button> Button 1 </button>
<button> Button 2 </button>
<button> Button 3 </button>

const buttons = document.getElementsByTagName("button");

for (var i = 0; i < buttons.lenght; i++) {
   const button = buttons[i]; 
   button.addEventListener ("click", function () {
      alert ("button " + i + " pressed"); 
   });
}

In this example we have a scope issue as var i belongs to global scope. We need to use the let keyword so that it lives inside the function. When I would run this code the button would always display i = 5 as this is the last value assigned after the loop finishes. 


--------------------------
When var
--------------------------
Keyword var is not recommended anymore. Usage of var keyword should be avoided as a good practice. 


--------------------------
Arrow Function // difference between function declaration and function expression
--------------------------

Function declaration with no arguments 
--------------------------
const name = "Andrew";

function sayName ()  {
    const message = "My name is " + name;
    console.log(message);
}

function sayBye () {
  console.log("Bye " + name);  
} 
--------------------------
Arrow fuction expression with no arguemnt
--------------------------

const name = "Andrew";

const sayName = () => {
    const message = "My name is " + name;
    console.log(message);
}

const sayBye = () => {
  console.log("Bye " + name);  
} 

Function declaration with 1 argument
--------------------------


function square(x) {
    return x * x;
}

function cube(x) {
    return square(x) * x;
}

--------------------------
Arrow fuction expression with 1 arguemnt
--------------------------

const square = (x) => {
    return x * x;
}

const cube(x) => {
    return square(x) * x;
}
--------------------------
Examples of how to shorten the code 
--------------------------

//Function Declaration

function divide1(a, b) {
  return a / b; 
}

//Function Expression

const divide2 = function(a, b) {
  return a / b;
}

//Arrow Function Expression

const divide3 = (a, b) => {
  return a / b;
}

//Arrow Function Expression - concise

const divide4 = (a, b) => a / b;
