# OBJECTS
1. Syntax of creating new objects:
	- `let user = new Object(); // "object constructor" syntax`
	- `let user = {};  // "object literal" syntax`


| JavaScript Objects | JSON | Python Dictionaries |
|--------------------|------|----------------------|
| Core data structures in JavaScript used to store key-value pairs. | A data *format*, not a language feature. | Built-in Python data type to store key-value pairs. |
| `const person = { name: "Alice", age: 30, isAdmin: true };` | `{ "name": "Alice", "age": 30, "isAdmin": true }` | `person = { "name": "Alice", "age": 30, "is_admin": True }` |
| `const jsonString = JSON.stringify(person);`<br>`const obj = JSON.parse(jsonString);` | Used for data exchange only, not actual code execution. | `import json`<br>`json_string = json.dumps(person)`<br>`data = json.loads(json_string)` |
|Strings, Symbols|Strings only|Immutable types|

# OBJECTS
1. Syntax of creating new objects:
	- `let user = new Object(); // "object constructor" syntax`
	- `let user = {};  // "object literal" syntax`


| JavaScript Objects | JSON | Python Dictionaries |
|--------------------|------|----------------------|
| Core data structures in JavaScript used to store key-value pairs. | A data *format*, not a language feature. | Built-in Python data type to store key-value pairs. |
| `const person = { name: "Alice", age: 30, isAdmin: true };` | `{ "name": "Alice", "age": 30, "isAdmin": true }` | `person = { "name": "Alice", "age": 30, "is_admin": True }` |
| `const jsonString = JSON.stringify(person);`<br>`const obj = JSON.parse(jsonString);` | Used for data exchange only, not actual code execution. | `import json`<br>`json_string = json.dumps(person)`<br>`data = json.loads(json_string)` |
|Strings, Symbols|Strings only|Immutable types|


2. To access a property, we can use:
	- The dot notation: `obj.property`.
	- Square brackets notation `obj["property"]`. Square brackets allow taking the key from a variable, like `obj[varWithKey]`.
3. Additional operators:
	- To delete a property: `delete obj.prop`.
	- To check if a property with the given key exists: `"key" in obj`.
	- To iterate over an object: `for (let key in obj) loop`.
4. Property names limitations
	- As we already know, a variable cannot have a name equal to one of the language-reserved words like `“for”, “let”, “return”` etc.
	- There’s a minor gotcha with a special property named `__proto__`. We can’t set it to a non-object value.
	- `let obj = {};` <br>
`obj.__proto__ = 5; // assign a number`<br>
`alert(obj.__proto__); // [object Object]`
5. Property existence test, “in” operator :
	- Reading a non-existing property just returns `undefined` 
	- `let user = {};`<br>
`alert( user.noSuchProperty === undefined ); // true means "no such property"`
	- There’s also a special operator `"in"` for that.
	`let user = { name: "John", age: 30, text:undefined };` <br>
`alert( "age" in user ); // true, user.age exists` <br>
`alert( "blabla" in user ); // false, user.blabla doesn't exist` <br>
`alert("text" in user); //true, user.text exist even though it is declared as undefined`
6. Ordered like an object:
	- “ordered in a special fashion” integer properties are sorted, others appear in creation order.
	- As an example, let’s consider an object with the phone codes:
	`let codes = {
  "49": "Germany",
  "41": "Switzerland",
  "44": "Great Britain",
  // ..,
  "1": "USA"
};`<br>
`for (let code in codes) {
  alert(code); // 1, 41, 44, 49
}`
	- Adding a plus "+" sign before each code is enough
	`let codes = {
  "+49": "Germany",
  "+41": "Switzerland",
  "+44": "Great Britain",
  // ..,
  "+1": "USA"
};`<br>
`for (let code in codes) {`<br>
  `alert( +code ); // 49, 41, 44, 1`<br>
  `alert( code ); // +49, +41, +44, +1`<br>
`}`
