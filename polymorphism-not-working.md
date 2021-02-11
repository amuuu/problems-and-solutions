### P: Polymorphism not working
- Project: [Ava](https://github.com/funktional-stdo/ava)

#### Description:

Suppose `BaseClass` has a bunch of childs and I wanted to have a collection of its child's objects. So naturally I created a list with the `BaseClass` type. Logically, when adding objects to the list polymorphism should happen and when you want to access an object inside the list and call a function of that object, you expect that the function from that **child class** will be called but it was not working as I was expecting.

#### Solution that worked:

Turned out that the solution was purely based on syntax;

```
// this is a normal method
void a() { /* stuff */ }

// this makes a class abstract.
virtual void a() = 0;

// this lets polymorphism happen the way I want; 
virtual void a() { }
```

In the third case, the child class overrides the method in this way:
```
void a() { /* childs content */ }
```
And when you write a child object on a parent object and call the method `a()`, the child's implementation will be called.
