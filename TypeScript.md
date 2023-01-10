TypeScript

TypeScript offers everything JavaScript does, with an additonal layer on top: the "type system". 

For example, JavaScript provides language primitives like string and number, but it doesn’t check that you’ve consistently assigned these. TypeScript does.

-> This means that your existing working JavaScript code is also TypeScript code. The main benefit of TypeScript is that it can highlight unexpected behavior in your code, lowering the chance of bugs.

You may have written JavaScript in Visual Studio Code, and had editor auto-completion. Visual Studio Code uses TypeScript under the hood to make it easier to work with JavaScript.



Types by Inference

TypeScript knows the JavaScript language and will generate types for you in many cases. For example in creating a variable and assigning it to a particular value, TypeScript will use the value as its type.

You can use a wide variety of design patterns in JavaScript. However, some design patterns make it difficult for types to be inferred automatically (for example, patterns that use dynamic programming). To cover these cases, TypeScript supports an extension of the JavaScript language, which offers places for you to tell TypeScript what the types should be.

For example, to create an object with an inferred type which includes name: string and id: number, you can write:

const user = {
  name: "Hayes",
  id: 0,
};

You can explicitly describe this object’s shape using an interface declaration:

interface User {
  name: string;
  id: number;
}

If you provide an object that doesn’t match the interface you have provided, TypeScript will warn you:

interface User {
  name: string;
  id: number;
}
 
const user: User = {
  username: "Hayes",
Type '{ username: string; id: number; }' is not assignable to type 'User'.
  Object literal may only specify known properties, and 'username' does not exist in type 'User'.
  id: 0,
};

There is already a small set of primitive types available in JavaScript: boolean, bigint, null, number, string, symbol, and undefined, which you can use in an interface. TypeScript extends this list with a few more, such as any (allow anything), unknown (ensure someone using this type declares what the type is), never (it’s not possible that this type could happen), and void (a function which returns undefined or has no return value).

You’ll see that there are two syntaxes for building types: Interfaces and Types. You should prefer interface. Use type when you need specific features.




-------------------COLT STEELE TS COURSE-------------------

Purpose of the language: Typescript seeks to fill in the bugs that are inherent in javascript. 

Terms: 
Static checking : Looks to detect errors in the code without even running it. It doesn't execute any code, it just looks at it and checks before runtime. 

It's a type checker: It can find the data and know what type it should be. 

The whole point is to help us find and fix errors before our code even runs. 

After the errors are resolved, the code is compiled into ordinary javascript. 



