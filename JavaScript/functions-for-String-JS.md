- .toUpperCase() -> is used to shift the string to uppercase
```
const example = 'hello, im francmirror';

console.log(example.toUpperCase());

output -> HELLO, IM FRANCMIRROR
```
- .toLowerCase() -> is used to shift the string to lowercase
```
let text1 = "IM FRANCMIRROR";

output -> "im francmirror"
```
- .indexOf(word) -> returns the index, within the calling String object, of the first occurrence of the specified value, starting the search from indexFrom; or -1 if no such value is found.
```
const imfrancmirror = ['hello', 'example', 'francmirror', 'js', 'git'];

console.log(imfrancmirror.indexOf('example'));
// Expected output: 1

<-- Start from index 2 -->
console.log(imfrancmirror.indexOf('example', 2));
// Expected output: 4

console.log(imfrancmirror.indexOf('python'));
// Expected output: -1
```

- .charAt(0) -> returns in a new String the number selected in a string.
```
let text = "HELLO WORLD";  
let char = text.charAt(0);

// Expected output: "H"
```
- .lenght ->  represents the length of a string
```
const str = 'Hello, I'm francmirror';

console.log(`${str} ${str.length}`);
// Expected output: "Hello, Im francmirror 21"
```
- .slice() -> extracts a part of a string and returns the extracted part in a new string.
```
let text = "git, example, francmirror";
let part = text.slice(7,13);

// Expected output: "ample,";
```

- .substring() -> is similar to `slice()`. The difference is that start and end values less than 0 are treated as 0 in `substring()`.
```
let str = "example, francmirror, git";  
let part = str.substring(7, 13);

// Expected output: ", fran"
```
- .substr() -> `substr()` is similar to `slice()`. The difference is that the second parameter specifies the **length** of the extracted part.
```
let str = "example, francmirror, git";   
let part = str.substr(7, 6);

// Expected output: ", fran"
```
- .replace() -> method replaces a specified value with another value in a string
```
let text = "I'm Francmirror";  
let newText = text.replace("Francmirror", "FranciscoE");

// Expected output: "I'm FranciscoE"
```
- ReplaceAll() -> method allows you to specify a regular expression instead of a string to be replaced.
```
let text = "I love cats. Cats are very easy to love. Cats are very popular."
text = text.replaceAll("Cats","Dogs");
text = text.replaceAll("cats","dogs");

// Expected output: "I love dogs. Dogs are very easy to love. Dogs are very popular."
```
- .concat() -> joins two or more strings
```
let text1 = "Hello";  
let text2 = "World";  
let text3 = text1.concat(" ", text2);

// Expected output: "Hello World!"
```
- .trim() -> method removes whitespace from both sides of a string
```
let text1 = "      Hello World!      ";  
let text2 = text1.trim();

// Expected output: Length text1 = 22 | Length text2 = 12
```
- .split() -> A string can be converted to an array with the `split()` method
```
text.split(",")    // Split on commas  
text.split(" ")    // Split on spaces  
text.split("|")    // Split on pipe

// Expected output: Length text1 = 22 | Length text2 = 12
```