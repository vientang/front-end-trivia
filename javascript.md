#Javascript Questions

####What is Typescript and why would you use it? 
Typescript is a layer, that sits on top of Javascript. It's used to standardize some of Javascripts quirky behaviors like type coersion, gets encapsulation, ensures that proper types are passed appropriately, and helps maintain code in enterprise scale apps that may have thousands of lines of code. 

A super helpful use case for Typescript is being able to catch incorrect data types early in development. This enables a developer to correct the mistakes early so that they don't creep up later in production code or whatever. Creating classes is another good use case. This follows the object oriented programming approach and allows for encapsulation of constructors, types, and methods within classes. 

####What is duck typing?
It is way of type checking. Suppose I create a function, which takes any object as an input. I then call the objects speak() method, unknowing if the object actually has a speak() method. If it turns out that the object does have a speak() method, then great! If not, we'll get an error message. Ultimately, we don't care about what the object is rather we care about what the object can do. 

Duck Typing: ![duck](https://cdn.meme.am/instances/67471500.jpg)

##Explain Currying
The currying function is the process of transforming any given function, that returns a new function with the curried values attached. This is useful when you need to get values from one function in your app to be used in another part of your app. It's good to know that these curried functions can be chained throughout your app. 

A good use case is when there's a need to read files through node (readFile(path)). This allows you to get the values from node and pass that through another curried function somewhere else in your app. 

```
function currying(fn) {
  
  return function curryHelper() {
    const args1 = [].slice.call(arguments)
    if (args1.length === fn.length) {
      return fn.apply(null, args1)
    }
    else {
      return function() {
        const args2 = [].slice.call(arguments)
        return curryHelper.apply(null, args1.concat(args2))
      }
    }
  }
}

const multiply = currying(function(a, b, c) {
  return a * b * c
})

multiply(2,8)(1) // 16
```

##What's the difference between a variable that is: null, undefined or undeclared?

##What are the advantages and disadvantages of using Ajax?

##Explain how JSONP works (and how it's not really Ajax).

##Explain "hoisting".

##What is the difference between == and ===?

##How can you declare a class in Javascript?
