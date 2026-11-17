# Type Aliases vs. Interfaces in TypeScript

## Introduction
TypeScript provides two ways to describe the shape of data: type 
aliases and interface. Understnding their difference helps us to write
clear and maintainable code.

## Detailed Discussion
For example:

interface User {
  name: string;
  amount: number;
}

type Product = {
  title: string;
  serial: number;
};

In these examples, both describe the object structure.
However, a interface can be redeclare and can marge the both declaration.
If we declare the same interface more than once, TypeScript
combines its elements.

interface User {
  phone: number;
}

Now 'User' also has an 'phone' property. A type alias cannot be reopened
this way.
A type alias is more flexible when we need unions, intrsections,
tuples. For example:

type Status = "pending" | "ok" | "rejected";
type ID = string | number;

Interfaces can extend other interfaces, while types can combine
using intersections '&'. Both of them support extension, but their
syntax is difference.

## Conclusion

we can Choose 'interface' when describing object shapes, especially when we need them to be extended or merged. And we can Choose 'type' when defining
unions, tuples, primitives, or more type combinations. The most important thing is
to stay consistent with our project's convantions.
