##Difference between _prototype_ and _proto_

####For those who are impatient
>'_prototype_' is just a random name give to the _linkage_
>between a function and an _unnamed_ object that gets
>created at the time of function creation.

while
>'_proto_' is the prototypal linkage between the object
>referenced by the **this** keyword and the _prototype_
>of the function.

**Confused?**

Let me explain these terms with the help of an example.  
Consider the below code:  
```javascript
  function Foo(who) {
    this.me = who;
  }
  Foo.prototype.identify = function() {
    return "I am " + this.me;
  };

  var a1 = new Foo("a1");
  var a2 = new Foo("a2");

  a2.speak = function() {
    alert("Hello, " + this.identify() + ".");
  };
  a1.constructor === Foo;
  a1.constructor === a2.constructor;
  a1.__proto__ === Foo.prototype;
  a1.__proto__ === a2.__proto__;
```
Before anything gets executed in the above code
we already have somethings, which are:
1. A function called 'Object' (capital 'O')
2. An object which does not have any name, but a
  label named 'Object.prototype'.
  
![View Image](http://imgur.com/To1zgcG)
