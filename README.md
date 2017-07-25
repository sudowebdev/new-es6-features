# New ES6 features


## var, let and const

#### Summary
**let** keyword is also called as the **new var** in JS. So, **instead of using var, we can use let** (except in some special cases).  

***Minimize mutable state***:  Always remember this principle. You should use **const** keyword whenever you find no need of re-assigning that variable.  
This simple thing helps a lot while debugging your application.


## Literals in ES6

ES6 has 2 kinds of literals:

1. **Template literals (code)**: Multi-line string literals that support interpolation
2. **Tagged template literals (code)**: Function calls

## Template literals

### Intro
Template literals are **string literals** that can stretch **across multiple** lines and include **interpolated expressions** (inserted via **${···}**):

	const firstName = 'Jane';
	console.log(`Hello ${firstName}!
	How are you
	today?`);

	// Output:
	// Hello Jane!
	// How are you
	// today?


The literal itself is delimited by **backticks (`) (key below Esc)**, the interpolated expressions inside the literal are delimited by ${ and }. Template literals **always produce strings**.

### Escaping in template literals

The **backslash** is used for **escaping inside template literals**.
It enables you to mention **backticks** and **${** inside template literals:


	> `\``
	'`'
	> `$` // OK
	'$'
	> `${`
	SyntaxError
	> `\${`
	'${'
	> `\${}`
	'${}'

### Line terminators in template literals

Line terminators in template literals are **always LF (\n)**.

	const str = `BEFORE
	AFTER`;
	console.log(str === 'BEFORE\nAFTER'); // true


## Tagged Template literals

**Tagged template literals (short: tagged templates) are function calls whose parameters are provided via template literals**.  
 

###### It is important to keep in mind that the names of template literals and tagged templates are slightly misleading. They have nothing to do with templates, as often used in web development: text files with blanks that can be filled in via (e.g.) JSON data.

The following is a **tagged template literal** (short: tagged template):

	tagFunction`Hello ${firstName} ${lastName}!`

*Putting a template literal after an expression triggers a function call, similar to how a parameter list (comma-separated values in parentheses) triggers a function call.*  

The previous code is **equivalent** to the following **function call** (in reality, first parameter is more than just an Array, but that is explained later).

	tagFunction(['Hello ', ' ', '!'], firstName, lastName)

Thus, the name before the content in backticks is the **name of a function** to call, the **tag function**. The tag function receives two different kinds of data: 

1. Template strings such as 'Hello '.
2. Substitutions such as firstName (delimited by ${}). A substitution can be any expression.

Template strings are known **statically (at compile time), substitutions are only known at runtime**. 

The **tag function** can do with its parameters as it pleases: It can completely ignore the template strings, return values of any type, etc.


## For more information

**[Read this](http://wesbos.com/tagged-template-literals/)**


## Destructuring

## What is it?
Destructuring is a **new** feature of JavaScript that **allows to break-apart / destructure stuff into variables**. 


## How to use it?
See the example in **destructuring/destructuring.js**  

## When to use it?
**Common use-case** of destructuring is to **make it easier to deal with options object**.  
*By options object I mean object that you pass in a function which is a single object  that might or might not contain several properties.*  

See the implementation in **destructuring/use-case.js**

## For more
***[Click here](https://youtu.be/PB_d3uBkQPs?list=PL0zVEGEvSaeHJppaRLrqjeTPnCH6vw-sm)***
