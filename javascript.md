#Javascript Questions

####What is Typescript and why would you use it? 
Typescript is a layer, that sits on top of Javascript. It's used to standardize some of Javascripts quirky behaviors like type coersion, gets encapsulation, ensures that proper types are passed appropriately, and helps maintain code in enterprise scale apps that may have thousands of lines of code. 

A super helpful use case for Typescript is being able to catch incorrect data types early in development. This enables a developer to correct the mistakes early so that they don't creep up later in production code or whatever. Creating classes is another good use case. This follows the object oriented programming approach and allows for encapsulation of constructors, types, and methods within classes. 

####What is duck typing?
It is way of type checking. Suppose I create a function, which takes any object as an input. I then call the objects speak() method, unknowing if the object actually has a speak() method. If it turns out that the object does have a speak() method, then great! If not, we'll get an error message. Ultimately, we don't care about what the object is rather we care about what the object can do. 

Duck Typing: ![duck](https://cdn.meme.am/instances/67471500.jpg)