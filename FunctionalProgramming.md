# functional programming

Functions: the functions are objects (data type)!~S

#  high order functions

features:

1. `easy to add feature` 
When we develop without taking this feature we brake the rule `DRY` don't repeat yourself. How do we improve and apply this rule to our code? with hig-order functions because we pass a function as an argument. This feature gives us the ability to manipulate the data depending on what functions do we pass

2. `more readable`
We define a function `copyArrayAndManipulate(mutiplyBy2)` and also `copyArrayAndManipulate(Add2)` we dont repeat code and reuse! this turn the code into more readable code

3. `easy to debbug` because we understand what is happening under-the-hood


## a callback or a high-order function?

1. callback: the function we pass
2. high-order function: the function that `takes in` a function or `returns` a function.


# pair programming

`What are the adventaje of pair programming?`

1. **you grow faster**:  When you are working alone, you can step away whenever you want. But when you got a pair programming partner, you can't step away; you have to do your whole challenges; and that where you grow. 
2. **technical communication**: 
One partner gives an overall strategy to approach each challenge, 
The other partner will have the responsability to write the solution and 
This will give you a more prceisly lenguage. 
3. **find errors** errors are no longer a mistery. 


# arrow functions

These pieces of codes have the same effects

I am declaring a function `func`:
0000000
```
const func = (input) => { return input * 2 }
const func = (input) => input * 2
const func = input => input * 2
```

# arrays have access to `methods` ?

An array is an object, for example `a=[1,2,3]`. You can add elements in the array with `a.push(4)` for example. Although this is an object with the property `push`, what that's means? 
The object has a property `__proto__` and it contains this functions buuut this property does not contains the functions (we dont need a copy each time), this property contains a reference to a globa object. This global object has the following properties with functions:

```
{ push: aFunction, map: aFunction, reduce: aFunction, filter: aFunction, ...}
```

How the chain works? When JS doesnt find a method on the object, JS looks up into the `__proto__` property. 

```
var arr = [1,2,3];
arr.reduce(add 0);
```
Chain of execution: (arr are objects data type)
1. JS looks inside arr object. Does JS find it? No
2. Where does JS looks instead? into `__proto__` property
3. What does JS finds here? a reference to a globa object
4. JS looks insede the global object and find the property `reduce` with the corresponding value (function)
5. JS executes the function.
6. How does JS access to the array [1,2,3]? With the keyword `this`

The label is `Array.prototype.reduce` for example.