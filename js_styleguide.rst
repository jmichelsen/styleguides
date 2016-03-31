Programming Style Guide
===============================

The focus of this style guide is to keep consistency among developers in the team. A style guide for Javascript does not yet exist.  If you have questions about style and do not see a discussion in this guide ask a developer then add content to this guide.

JS Standards
-----
- Break a style rule if applying the rule would make the code less readable.

- Avoid global variables. Some Exceptions:

    - Constants, i.e. PI = 3.14159.  Constants should be named using all caps with underscores.
    - If needed, globals should be made internal to the module and accessed through public module level functions.

- Use the implicit false if possible.
  Take advantage of "falsey" behavior in Javascript.

    Yes:
        if (user) {
            // Do something
        }

    No:
        if (user.length == 0) {
            // Do something
        }

- Use 4 spaces per indentation level. **Not a tab character**.
- Limit all lines to a **maximum** of 100 characters.
- Do not use compound statements (multiple statements on the same line).
- No white-space directly before end of line. Including empty lines of code.
- Ensure there is at least one empty line at the end of a file.
- Use a trailing comma on associative arrays and object literals.

Code Length
-----
Due to the nature of Javascript a great deal of anonymous functions are used.  Therefore it is difficult to define how long code should be before it should be refactored.  In this case it's best to use good judgment.  If the reader begins to lose track of the purpose of a block of code before they are finished getting through it - your code is too long and you need to refactor.  Generally, all functions/methods/blocks of code should be less than 30-35 lines (including comments).

Never make the reader scroll down on their editor to read your block of code.


Comments
-----
- Comment at the beginning of each file to advise the reader to the general purpose of the file. Use a single paragraph to outline the use of the file within the system.  If more than one paragraph should be used the code should be refactored into more files.

- Inline commenting is discouraged but may be used sparingly if the comment + code doesn't exceed the maximum line length.

- Comments should be used on any logic that is not immediately obvious to a junior developer upon inspection.  If a comment is to be used that comment should exist one line prior to the code being described.  Multiple line comments are discouraged as it's an indication the code is getting too complicated.  If this is the case, try to refactor.

Spacing
-----
The spacing used in your code makes a considerable difference in the readability of your code. As such, an section is devoted entirely to ensure spacing rules are followed. Avoid extraneous whitespace in the following situations:

- Immediately inside parentheses, brackets or braces.

      Yes: var foo = [1, 2, 3];
      No:  var foo = [ 1, 2, 3 ];

- Immediately before a comma or semicolon.

      Yes: var foo = [1, 2, 3];
      No:  var foo = [1 , 2 , 3] ;

- Immediately before the open parenthesis that starts the argument list of a function call.

      Yes: var foo = bar(a, b);
      No:  var foo = bar (a, b);

- Immediately before the open parenthesis that starts an indexing.

      Yes: var foo = someList[index];
      No:  var foo = someList [index];

- Use spaces immediately after colon when defining associative array.

      Yes:
        var foo = {
            key: 'value',
        }
      No:
        var foo = {
            key:'value',
        }

- Use spaces before and after colon when used with ternary operators.

      Yes:
        a = typeof a !== 'undefined' ? a : 42;
      No:
        a = typeof a !== 'undefined' ? a:42;

- Use spaces around arithmetic, comparison and binary operators.

    Yes: var foo = a + b;
    No:  var foo = a+b;

- Function definitions should have their opening brace on the same line as the name with a single space separating them.

    Yes:
      function foo(a, b) {
          // Do something
      }
    No:
      function foo(a, b){
          // Do something
      }
    No:
      function foo(a, b)
      {
          // Do something
      }

- If statements and for loops are not functions.  Use proper spacing.  One space after 'if' or 'for' syntax.  One space before opening brace.  First brace should be placed on the same line as the 'if' or 'for' syntax.

    Yes:
      if (foo === true) {
          // Do something
      }
    No:
      if(foo === true){
          // Do something
      }

- Else statements may share the line with the previous closing brace.

    Yes:
      if (foo === true) {
          // Do something
      }
      else {
          // Do something else
      }
    Yes:
      if (foo === true) {
          // Do something
      } else {
          // Do something else
      }
    No:
      if (foo === true) {
          // Do something
      }else{
          // Do something else
      }

- If a comment is necessary for an else condition do not try to embed the comment.

    Yes:
      if (foo === true) {
          // Do something
      }
      // Commment
      else {
          // Do something else
      }
    No:
      if (foo === true) {
          // Do something
      // Comment
      } else {
          // Do something else
      }


- Use a single empty line to separate blocks of code within a function.

    Yes:
      function foo(a, b) {
        if (a === true) {
            // Do something
        }

        if (b === true) {
            // Do something
        }
      };
    No:
      function foo(a, b) {
        if (a === true) {
            // Do something
        }
        if (b === true) {
            // Do something
        }
      };

- Use two empty lines to separate function definitions and other file-level code blocks.

    Yes:
      function foo(a, b) {
          // Do something
      };


      function bar(a, b) {
          // Do something
      }
    No:
      function foo(a, b) {
          // Do something
      };

      function bar(a, b) {
          // Do something
      }

- Readability is more important than line efficiency.  If defining associative arrays within a function call setup new lines for definitions with spacing offset by four spaces.

    Yes:
      response += Broadcasts.find({
          $and: [
              {page: page._id},
              {time: {
                  $gt: gate,
                  $lt: now
              }}
          ]}).count();
    No:
      response += Broadcasts.find({$and: [{page: page._id}, {time: {$gt: gate, $lt: now}}]}).count();



Naming
-----
The naming convention should be consistent throughout the entire project.

- Variables use lowerCamelCase.
- Class objects use UpperCamelCase.
- Functions and methods use lowerCamelCase.
- Constants use UNDERSCORED_CAPS.

