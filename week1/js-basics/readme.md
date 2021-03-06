## Introduction to JS
> A programming language is a language that lets you give instructions to a computer.

In English, we write **SENTENCES**, composed of **WORDS**, which have **TYPES** (noun, verb).

In JavaScript, we write **STATEMENTS**, composed (mostly) of **VALUES**, which have **TYPES** (Number, String).

As far as punctuation goes in this analogy, the `;` is the period of a sentence, though in JavaScript, they are optional.

### Comments
> Comments give developers the ability to write sentences in a spoken language (English, etc)

In JS, there are two ways to write comments:

```javascript
    // use double forward slashes for a single line comment
    /*
        forward slash followed by an asterisk will open a multi-line comment,
        and an asterisk will close a multi-line comment
     */
```

Comments are amazing! Write tons of them!

### Variables
> Variables refer to values. Variables are created with the keyword `var` and assigned with the `=` operator.

```javascript
    var foo
    var iLikeCamels = 1
    var snakes_are_awesome = 'snakes'
```

#### Valid variable names
> A variable name must start with a letter, underscore, or $. After the first character, it can also have numbers.

* Valid
    - `foo`
    - `result`
    - `result2`
    - `__secret`
    - `$$billz`
* Invalid
    - `2fast2furious`
    - `me&you`
    - `0`
    - `awesome-things-and-stuff`

### Reserved keywords

[https://mathiasbynens.be/notes/reserved-keywords](Reference: Reserved Keywords by JS Versions)

#### ES5 Keywords (In the context of the Browser)
- `arguments`
- `break`
- `case`
- `catch`
- `class`*
- `const`*
- `continue`
- `debugger`
- `default`
- `delete`
- `do`
- `else`
- `enum`
- `eval`
- `export`***
- `extends`*
- `false`
- `finally`
- `for`
- `function`
- `if`
- `implements`*
- `import`***
- `in`
- `Infinity`
- `instanceof`
- `interface`*
- `let`**
- `NaN`
- `new`
- `null`
- `package`*
- `private`*
- `protected`*
- `public`*
- `return`
- `static`*
- `super`*
- `switch`
- `this`
- `throw`
- `true`
- `try`
- `typeof`
- `undefined`
- `var`
- `void`
- `while`
- `with`
- `yield`**

`*` Reserved, but not implemented in ES5
`**` Available for use when strict mode is ON
`***` Can be **transpiled** into ES5

### Primitive Types
> These are the different basic types of values that exist in JavaScript. Think of these as types of building blocks.

```javascript
    Number // integers, decimals
    String // characters
    Boolean // true/false
    null (defined with a value of nothing)
    undefined (not even defined)
```

#### Numbers
> In JS, a `Number` can be represented as an `integer` or a `float`.

- **Literals** - Single most straight forward way to represent a number.
```javascript
    2 // deuce
    3.14159265359 // mmm, pi...
    1e6 // 1,000,000
```
- **PEMDAS** (order of operations), determines the order that math happens in
- **Operators**
```javascript
    + // addition
    - // subtraction
    * // multiplication, generators (advanced topic)
    / // division
    % // modulus
```

### Strings
> In JS, a `String` is a series of characters and can be empty (0 characters) up to potentially unlimited (though constrained by hardware).

- **Literals**
```javascript
    'a'
    '1'
    'cats'
    'hello!'
    'Man, donuts sound great right about now...'
    'A witty saying proves nothing.'
    'don\'t do this' // backslash ESCAPES the apostrophe, avoid escapes if at all possible (cleanliness)
    "Instead, use doubles quotes to escape contractions like don't, won't, and couldn't (but I still did)"
```
- **Operators**
```javascript
    + // concatenation
```

- **Properties**
    * because strings are Objects, they have accessible properties on them
    * you can access object properties using the `.` (dot notation)
    * all strings have a 'length' property, which tells you how long the string is
    * all strings have numerical indexes, which tell you what letter is at a particular location

```javascript
    var s='string'
    s.length // 6
    var s='string'
    s[0] // 's'
    s[1] // 't'
    // ...
```

### Booleans
> In JS, booleans are all about logic

- **Literals**
```javascript
    true
    false
```

**Operators**
```javascript
    !   // not
    !=  // not equal
    ==  // is equal
    === // is literally equal
    &&  // and
    ||  // or
    <   // less than
    <=  // less than or equal to
    >   // greater than
    >=  // greater than or equal to
```

### Conditional statements
> If statements are used to control conditions within the logic of your code.

#### If
**Example**: If I drink 3 cups of espresso, my eyes will twitch.
```javascript
    var cups = 3
    if( cups === 3 ) {
        console.log("Oy! My twitchin' eyes!")
    }
```

#### Else
Most of the time, you will likely if-else chains:
- chains start with exactly one if-statement
- can have zero to infinite else-if statements
- can have zero or one else statement ( but it is often better to include an else )

```javascript
    var cups = 0
    var shots = 1

    cups = shots * 3

    if ( cups === 0 ) {
        console.log('ZzzzZzz')
    } else if ( cups === 1 ) {
        console.log('Good morning! :D')
    } else if ( cups === 2 ) {
        console.log('Time to cut back...')
    } else if( cups === 3 ) {
        console.log("Oy! My twitchin' eyes!")
    } else {
        console.log('GAAAAAAAH!')
    }
```

#### Truthey && Falsey values
In JS, there are several values that are considered falsey, (resolves as false within `if` conditional statements)

- `0` and `NaN` are falsey. all other numbers are truthey.
- `''` is falsey. all other strings are truthey.
- `null` && `undefined` are always falsey.
- all other values are truthey.

#### Switch statements
Just like if statements, with slightly different capabilities and structure.

```javascript
    var cups = 0
    var shots = 1

    cups = shots * 3

    switch( cups ) {
        case  0: console.log('ZzzzZzz'); break
        case  1: console.log('Good morning! :D'); break
        case  2: console.log('Time to cut back...'); break
        case  3: console.log("Oy! My twitchin' eyes!");  break
        default: console.log('GAAAAAAAH!'); break
    }
```
