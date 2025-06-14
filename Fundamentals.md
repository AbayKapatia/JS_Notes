# JavaScript
Let us explore JavaScript
## Data Types
1. Infinty
2. NaN (it is sticky : exception `NaN ** 0 == 1`)
3. null ( `typeof null` -> object which is internally recognized error )
4. undefined
5. BigInt ( `998877655433321112333n` here n represents BigInt)
6. String(`" "`, `' '`,\`&{}\`)
7. Boolean (true / false)
8. Object
9. Symbol for unique identifiers.
## Interaction
1. alert
2. prompt ( `prompt(text,[value_default])` )
3. confirm
## Conversion
1. alert automatically converts to String: ` let value = true; alert(value); // true is String now`
2. String Conversion: `String(x)`
3. Numeric conversion: `alert("6"/"2") // 3` or `Number(x)` or `alert(6-'2');//4`
4. unary +: It actually does the same thing as  `Number(...)`, but is shorter.
`// Converts non-numbers`
`alert( +true ); // 1`
`alert( +"" );   // 0`
`alert( +apples + +oranges ); // 5`

> 	 | Value | Becomes… 	 |`undefined` -> `NaN` 	 |`null` -> `0` 	 |`true
> and false` -> `1`  and  `0` 	 |`string` -> Whitespaces (includes spaces,
> tabs  `\t`, newlines  `\n`  etc.) from the start and end are removed.
> If the remaining string is empty, the result is  `0`. Otherwise, the
> number is “read” from the string. An error gives  `NaN`.

5. Boolean Conversion: `Bollean("",0,undefined,null,NaN) -> false`
## Basic Operators
1. Urinary operator
2. Binary operator 
3. Assignment operator : `let c = 3 - (a = b + 1); //0 as b=2` or `a = b = c = 2 + 2;`
4. Increment AND Decrement
5. Comma : `let a = (1 + 2, 3 + 4); //7`
## Comparison
1. Equality operator: `==`
`let a = 0;
let b = "0";
alert( Boolean(a) ); // false
alert( Boolean(b) ); // true
alert(a == b); // true!`
IMP:->`alert( null == undefined ); //true`
2. Strict Equality Operator: `===`
`alert( 0 === false );`
IMP:->`alert( null === undefined ); //false`
3. Comparison btw undefined and null and 0: (The reason is that an equality check `==` and comparisons `> < >= <=` work differently. Comparisons convert `null` to a number)
`alert( null > 0 );  // (1) false
alert( null == 0 ); // (2) false
alert( null >= 0 ); // (3) true`
undefined and 0
`alert( undefined > 0 ); // false (1)
alert( undefined < 0 ); // false (2)
alert( undefined == 0 ); // false (3)`
## Condition if else
1. If , else, else if statement
`if (year < 2015) {
  alert( 'Too early...' );
} else if (year > 2015) {
  alert( 'Too late' );
} else {
  alert( 'Exactly!' );
}`
2.  Conditional operator '?'
`let result = condition ? value1 : value2;`
3. Some Examples:
	- `let message = (age < 3) ? 'Hi, baby!' :
  (age < 18) ? 'Hello!' :
  (age < 100) ? 'Greetings!' :
  'What an unusual age!';`
	 - `(company == 'Netscape') ?
   alert('Right!') : alert('Wrong.');`
   - `(i > 5) ? alert(i) : continue; ` continue isn't allowed here nor break in loops.
  ## Logical Operator
  1. Or  ||
	  - **OR ||** finds the first truthy value
`let firstName = "";
let lastName = "";
let nickName = "SuperCoder";
alert( firstName || lastName || nickName || "Anonymous"); // SuperCoder
`
	  - Short-circuit evaluation.
  2. && (AND)
	 - **AND &&** finds the first falsy value
`result = value1 && value2 && value3;`
3. ! (NOT) 
4. ? ? ( Nullish Coalescing) 
	- `??` returns the first argument if it’s not `null/undefined`. Otherwise, the second one.
	- Select the first value from a list that isn’t null/undefined:
	`let firstName = null;
let lastName = null;
let nickName = "Supercoder";
// shows the first defined value:
alert(firstName ?? lastName ?? nickName ?? "Anonymous"); // Supercoder`
	- Comparison with ||:
	`let height = 0;
alert(height || 100); // 100
alert(height ?? 100); // 0`
## Loops
1. while loop:
	- `while (i != 0)` can be `while (i)`
	- `while (i) { // when i becomes 0, the condition becomes falsy, and the loop stops`
  `alert( i );`
  `i--;
}`
	- if the loop body has a single statement, we can omit the curly braces `{…}`:
	`while (i) alert(i--);`
2. do...while loop:
	- The loop will first execute the body, then check the condition, and, while it’s truthy, execute it again and again.
	- `do {
alert( i );`
  `i++;
}` 
`while (i < 3);` 
3. for loop:
	-  `for (let i = 0; i < 10; i++) {
  if (i % 2) {
    alert( i );
  }
}`
4. Labels for break/continue: 
	- A label is an identifier with a colon before a loop:
		- Syntax:
`labelName: for (...) {
  ...
}`
		- Example:
`outer: for (let i = 0; i < 3; i++) {
  for (let j = 0; j < 3; j++) {
    let input = prompt(`Value at coords (${i},${j})`, '');
    // if an empty string or canceled, then break out of both loops
    if (!input) break outer; // (*)
    // do something with the value...
  }
}
alert('Done!');`
## Switch
1. A  `switch`  statement can replace multiple  `if`  checks. It gives a more descriptive way to compare a value with multiple variants.
	- Type matching is strict and can group cases too:
	`switch (a) {`
 ` case 3:`// grouping of case 3 and 4
 ` case 4:`
 `   alert( 'Exactly!' );`
 `   break;`
 ` case 5:`
  `  alert( 'Too big' );`
 `   break;`
`  default:`
`    alert( "I don't know such values" );`
`}`
## Function
1. Function Defination:
	- `function name(parameter1, parameter2, ... parameterN) {
 // body
}`
	- Default Parameters: 
 `function showMessage(from, text = "no text given") {
  alert( from + ": " + text );
}`
	- Return Value in function,. Function without return have undefined as its returned value.
	`function sum(a, b) {
  return a + b;
}`

|Function Declarartion|Function Expression  |
|--|--|
| `function sayHi() {alert( "Hello" );}` |  `let sayHi = function() {alert( "Hello" );};`    |
|A Function Declaration can be called earlier than it is defined.|A Function Expression is created when the execution reaches it and is usable only from that moment.|
|`let age = prompt("What is your age?", 18); if (age < 18) {  function welcome() {    alert("Hello!");  } } else {  function welcome() {    alert("Greetings!");  } }// ...use it later welcome(); // Error: welcome is not defined`|`let age = prompt("What is your age?", 18);let welcome; if (age < 18) { welcome = function() {    alert("Hello!"); };} else {  welcome = function() {    alert("Greetings!");};}welcome(); // ok now`
|
### NOTE: 
`function sayHi() {`
 ` alert( "Hello" );
}`
`alert( sayHi ); // shows the function code
`
Please note that the last line does not run the function, because there are no parentheses after  `sayHi`. There are programming languages where any mention of a function name causes its execution, but JavaScript is not like that.
In JavaScript, a function is a value, so we can deal with it as a value. The code above shows its string representation, which is the source code.
Surely, a function is a special value, in the sense that we can call it like  `sayHi()`.
But it’s still a value. So we can work with it like with other kinds of values.

### Condition declaration
`let age = prompt("What is your age?", 18);`
`let welcome = (age < 18) ?`
 ` function() { alert("Hello!"); } :`
`  function() { alert("Greetings!"); };`
`welcome(); // ok now`

|Functional Expression|Arrow Function|
|--|--|
|`let func = function(arg1, arg2, ..., argN) {return expression;};`|`let func = (arg1, arg2, ..., argN) => expression;`|
|||

Some Examples:
1. Arrow Function with no parameters: 
`let sayHi = () => alert("Hello!");
sayHi();`
2. Arrow Function with one parameter:
`let double = n => n * 2;
// roughly the same as: let double = function(n) { return n * 2 }
alert( double(3) ); // 6`
3. Conditional Arrow Function:
`let welcome = (age < 18) ?
  () => alert('Hello!') :
  () => alert("Greetings!");
welcome();`

### Multiple Arrow Function:
We need to have {} brackets and a return statement:
`let sum = (a, b) => {  // the curly brace opens a multiline function
  let result = a + b;
  return result; // if we use curly braces, then we need an explicit "return"
};`


#### Excercise :
Convert this code to Arrow Function:
`function ask(question, yes, no) {
  if (confirm(question)) yes();
  else no();
}
ask(
  "Do you agree?",
  function() { alert("You agreed."); },
  function() { alert("You canceled the execution."); }
);`
Converted Function:
`let ask = (question, yes, no) => confirm(question) ? yes() : no();
ask(
'Do you agree?',
() => alert('You agreed'),
() => alert('You interrupted execution'),
);`
