# General Notes

## General Info About Javascript
- Nodejs is a Javascript runtime, which understands how to interpret the code.
- There are many ways of reducing spaces in naming of variables:
   - **Snake Case**: Using underscores instead of spaces. (number_of_eggs)
   - **Camel Case**: Using a capital letter at the beginning of each word. (numberOfEggs) 
> The bottom line is you need to keep consistent and maintain only one of those styles per project.
- Semicolons are **NOT** required, but are included for code organization and by best practice.
- JS is a pass-by-value language!
- JS is indexed starting from ZERO.
- Not invoking the method `e.g. console.log` will not run anything and will not cause errors. You need to use `()`.
- Comma separated args of console.log have a space between them by default.

## Variables
- There are three keywords used to initialize variables:
    - **var**: Not really used a lot. The others are used more often.
    - **let**: A normal variable that might change later.
    - **const**: When value is never going to change in the program.
- You can only assign variables once.
- Assigning to a const causes an error.

## Data Types
- Number: `123456`
- String: `'mom'`
- Undefined
- Boolean: `true or false`
- Object: `{key: value}`
- Arrays: `[1, 2, 3, 4]`
  
## Functions
Functions allow reusability of code and are very important to reduce redundancy and refactor codes.
``` javascript
function myFirstFunction(value, secondValue) {
    console.log(value * secondValue);
}
```
This is a weird thing about JS. If we continue from the code above:
``` javascript
let multiplyTwoNumbers = myFirstFunction;
multiplyTwoNumbers(3, 5);
```
## Operators
- **Arithmetic**: +, -, /, *, %
- **Comparison**: ==, >, <, >=, <=, !=, === (checks type equality besides the soft), !==

```javascript
'6' == 6 // true
'6' === 6 // false
```

- **Logical**: &&, ||, !

## Control Flow

As for all languages, the conditions and loops are the essential parts.

## Basic Functions

A very weird thing that I encountered is shown below.
```javascript
function addStrings(string1, string2) {
    if (!string1 || !string2) {
        console.log('You are missing an input.');
        return; // exits function
    }

    let concatString = string1 + ' ' + string2;
    console.log(concatString);
}
addStrings('hello', 'mum'); // adds Space by default
addStrings('hello'); // Runs !!!
```
To avoid this situation, you could simply put default values.
```javascript
function addStrings(string1 = 'default1', string2 = 'default2') {
    if (!string1 || !string2) {
        console.log('You are missing an input.');
        return; // exits function
    }

    let concatString = string1 + ' ' + string2;
    console.log(concatString);
}
```

