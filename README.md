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

--------------------------
When let
--------------------------
let should be used when I want to reassign a value. It works like var. 

const person = {
            first_name: "Andrew",
            role: "Teacher"
        }
    
        function personDescription(person) {
            var description = person.first_name;
            if(person.role) {
                description = description + " is a ";
                description = description + person.role;
            }
            console.log(description);
        }
    
        personDescription(person);
