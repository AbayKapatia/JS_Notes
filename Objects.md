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
