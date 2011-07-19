Slang
-----
A collection of utility functions for working with strings in JavaScript in the browser or CommonJS.

## Node Installation
    npm install slang
    
## Annotated source code
The annotated source code for slang, generated by [Docco](http://jashkenas.github.com/docco/), 
can be found [here](http://devongovett.github.com/slang/).
    
## API

### slang.isString
Returns whether `input` is a string

    slang.isString('testing'); // true
    slang.isString(543);       // false
    
### slang.capitalize
Capitalizes the first character of a string

    slang.capitalize('hello world!'); // "Hello world!"
    
### slang.uncapitalize
Uncapitalizes the first character of a string

    slang.uncapitalize('Hello world!); // "hello world!"
    
### slang.capitalizeWords
Capitalizes each word in the string

    slang.capitalizeWords('hello world!'); // "Hello World!"
    
### slang.uncapitalizeWords
Uncapitalizes each word in the string

    slang.uncapitalizeWords('Hello World!'); // "hello world!"
    
### slang.isUpperCaseAt
Returns whether the character at the provided character index is upper case.

    slang.isUpperCaseAt('Testing', 0); // true
    
### slang.isLowerCaseAt
Returns whether the character at the provided character index is lower case.

    slang.isLowerCaseAt('Testing', 1); // true
    
### slang.swapcase
Inverts the case for each letter in the string

    slang.swapcase('aaBBccDD'); // "AAbbCCdd"
    
### slang.camelize
Converts a string of words seperated by dashes or spaces to camelCase

    slang.camelize('hello world'); // "helloWorld"
    slang.camelize('hello-world'); // "helloWorld"
    
### slang.dasherize
Converts a string of words or a camelCased string into a series of words separated by a dash (`-`)

    slang.dasherize('this is dashed'); // "this-is-dashed"
    
### slang.repeat
Concatenates the string `count` times

    slang.repeat('Ho! ', 3); // "Ho! Ho! Ho! "
    
### slang.insert
Inserts `string` in `input` at `index`

    slang.insert('this is cool!', 'really ', 8); // "this is really cool!"
    
### slang.remove
Removes the characters between the `start` and `end` indexes

    slang.remove('this is really cool!', 8, 15); // "this is cool!"
    
### slang.chop
Removes the last character of `input`

    slang.chop('hello'); // "hell"
    
### slang.trim
Removes leading and trailing whitespace from `input`.  Uses ES5's native trim is available.

    slang.trim('hello '); // "hello"
    
### slang.trimLeft
Removes the leading whitespace from `input`

    slang.trimLeft(' hello '); // "hello "
    
### slang.trimRight
Remove the trailing whitespace from `input`

    slang.trimRight(' hello '); // " hello"
    
### slang.join
Joins an array into a humanized list.  The last element is joined by "and" by default, but you can change it.

    slang.join(['red', 'blue', 'green']);       // "red, blue and green"
    slang.join(['red', 'blue', 'green'], 'or'); // "red, blue or green"
    
### slang.contains
Returns whether `input` contains `string`

    slang.contains('hello world', 'world'); // true

### slang.startsWith
Returns whether `input` starts with `string`

    slang.startsWith('hello world', 'hello'); // true
    
### slang.endsWith
Returns whether `input` ends with `string`

    slang.endsWith('hello world', 'world'); // true
    
### slang.isBlank
Returns whether `input` is empty or only contains whitespace

    slang.isBlank(' '); // true
    slang.isBlank('');  // true
    
### slang.successor
Returns the successor to str. The successor is calculated by incrementing characters starting 
from the rightmost alphanumeric (or the rightmost character if there are no alphanumerics) in the
string. Incrementing a digit always results in another digit, and incrementing a letter results in
another letter of the same case.

If the increment generates a carry, the character to the left of it is incremented. This 
process repeats until there is no carry, adding an additional character if necessary.

    slang.successor("abcd");      // "abce"
    slang.successor("THX1138");   // "THX1139"
    slang.successor("<<koala>>"); // "<<koalb>>"
    slang.successor("1999zzz");   // "2000aaa"
    slang.successor("ZZZ9999");   // "AAAA0000"

### slang.guid
Returns a unique guid of the specified length, or 32 by default

    slang.guid();   // "gE9FEtJknQVy3qkN9fxmTucYKTwFOno2"
    slang.guid(15); // "b0apU4OH7ZgmEoU"
    
### slang.addToPrototype
Adds the methods from the slang object to String.prototype.  Does not add slang.guid, slang.isString, slang.version, or itself.

    slang.addToPrototype();
    "test".capitalize(); // "Test"
    
## License

slang is licensed under the MIT license.